# NimbleScribe — Release Guide

Step-by-step process for shipping a new version of NimbleScribe on macOS and Windows.

---

## Table of Contents

- [Asset naming rules — read first](#asset-naming-rules--read-first)
- [Prerequisites](#prerequisites)
- [Release process overview](#release-process-overview)
- [Step 1 — Bump the version](#step-1--bump-the-version)
- [Step 2 — Build macOS (manual, on your Mac)](#step-2--build-macos-manual-on-your-mac)
- [Step 3 — Build Windows (automatic via GitHub Actions)](#step-3--build-windows-automatic-via-github-actions)
- [Step 4 — Create the GitHub Release](#step-4--create-the-github-release)
- [Step 5 — Update appcast.json](#step-5--update-appcastjson)
- [Step 6 — Verify end-to-end](#step-6--verify-end-to-end)
- [Versioning convention](#versioning-convention)
- [Rollback procedure](#rollback-procedure)

---

## Asset naming rules — read first

> **Both assets must use exact filenames — no version numbers.**

| Platform | Asset name |
|----------|-----------|
| macOS | `NimbleScribe.dmg` |
| Windows | `NimbleScribe.msix` |

These exact filenames power the permanent one-click download URLs:

```
https://github.com/anikherenow/Nimblescribe-Releases/releases/latest/download/NimbleScribe.dmg
https://github.com/anikherenow/Nimblescribe-Releases/releases/latest/download/NimbleScribe.msix
```

GitHub's `/releases/latest/download/<name>` always resolves to the newest release's asset with that exact filename. A version suffix in the name (e.g. `NimbleScribe-0.2.1.dmg`) will break the permanent download links on the website and in the app's update checker.

---

## Prerequisites

### macOS build (one-time setup)

- [ ] `create-dmg` installed: `brew install create-dmg`
- [ ] Apple Developer Program membership *(for notarization)*
- [ ] Developer ID Application certificate installed in Keychain
- [ ] `xcrun notarytool` credentials stored: `--keychain-profile nimblescribe`
- [ ] Flutter for macOS installed and on `stable` channel

### Windows build (one-time setup)

- [ ] `RELEASES_PAT` secret added to the private `NimbleScribe` source repo
  — a GitHub Personal Access Token with `public_repo` scope, scoped to this releases repo
- [ ] The GitHub Actions workflow exists at `.github/workflows/build-windows.yml` in the source repo

Windows builds run **automatically** on GitHub's `windows-latest` runner — you do not need a Windows machine.

---

## Release process overview

```
1. Bump pubspec.yaml version          (source repo)
2. Build macOS DMG + notarize         (your Mac)
3. Push a version tag                 (source repo → triggers Windows CI)
4. Wait for CI to upload NimbleScribe.msix
5. Create GitHub Release here         (attach DMG + MSIX)
6. Update appcast.json                (demo-projects repo)
7. Verify end-to-end
```

---

## Step 1 — Bump the version

In the private `NimbleScribe` source repo, open `pubspec.yaml`:

```yaml
version: 0.2.1+4   # MAJOR.MINOR.PATCH+BUILD_NUMBER
```

Also update `msix_config.msix_version` to match (four-part format):

```yaml
msix_config:
  msix_version: 0.2.1.4   # matches version above
```

Commit and push to `main`:

```bash
git add pubspec.yaml
git commit -m "chore: bump version to 0.2.1+4"
git push
```

---

## Step 2 — Build macOS (manual, on your Mac)

### 2a — Flutter build

```bash
cd /path/to/NimbleScribe
flutter build macos --release
```

Output: `build/macos/Build/Products/Release/NimbleScribe.app`

### 2b — Create the DMG

> ⚠️ Output filename must be exactly `NimbleScribe.dmg`

```bash
create-dmg \
  --volname "NimbleScribe" \
  --window-pos 200 120 \
  --window-size 600 400 \
  --icon-size 100 \
  --icon "NimbleScribe.app" 175 190 \
  --hide-extension "NimbleScribe.app" \
  --app-drop-link 425 190 \
  "NimbleScribe.dmg" \
  "build/macos/Build/Products/Release/NimbleScribe.app"
```

### 2c — Sign the DMG

```bash
codesign \
  --sign "Developer ID Application: YOUR NAME (TEAM_ID)" \
  --verbose \
  "NimbleScribe.dmg"
```

### 2d — Notarize with Apple

```bash
xcrun notarytool submit "NimbleScribe.dmg" \
  --keychain-profile "nimblescribe" \
  --wait
```

Wait for `status: Accepted`. Then staple the notarization ticket:

```bash
xcrun stapler staple "NimbleScribe.dmg"
```

Verify:

```bash
spctl --assess --type open --context context:primary-signature "NimbleScribe.dmg"
# Expected output: "accepted"
```

You now have a signed, notarized `NimbleScribe.dmg` ready to attach to the release.

---

## Step 3 — Build Windows (automatic via GitHub Actions)

Push a version tag from the source repo to trigger the CI build:

```bash
git tag v0.2.1
git push origin v0.2.1
```

The workflow (`.github/workflows/build-windows.yml`) will:

1. Check out the source code on a `windows-latest` runner
2. Download the bundled binaries (`whisper-cli.exe`, `llama-cli.exe`, `llama-server.exe`, `ffmpeg.exe`) from their official GitHub releases
3. Run `flutter build windows --release`
4. Bundle the binaries beside `NimbleScribe.exe`
5. Run `dart run msix:create` to produce `NimbleScribe.msix`
6. Push `NimbleScribe.msix` to this releases repo and create a draft GitHub Release

**Estimated CI time:** 10–20 minutes on first run (binary downloads are cached on subsequent runs).

Monitor the build at: `https://github.com/anikherenow/NimbleScribe/actions`

Once CI completes, `NimbleScribe.msix` will be attached to the draft release in this repo.

---

## Step 4 — Create the GitHub Release

> If CI already created a draft release, open and edit it. Otherwise create a new one.

1. Go to **[Releases → Draft a new release](../../releases/new)**
2. **Tag:** `v0.2.1` *(select the tag you just pushed)*
3. **Title:** `NimbleScribe 0.2.1`
4. **Release notes** — use this template:

```markdown
## What's new in 0.2.1

- [Short bullet of the most impactful change]
- [Second change]
- [Bug fix if any]

**macOS:** requires macOS 13 Ventura or later · Apple Silicon (M1–M4)
**Windows:** requires Windows 10 or 11 (x64) · Enable Developer Mode before installing
```

5. **Attach assets:**
   - `NimbleScribe.dmg` ← built and notarized in Step 2
   - `NimbleScribe.msix` ← built by CI in Step 3 (may already be attached)

6. Click **Publish release**

The permanent download URLs will resolve immediately:

```
https://github.com/anikherenow/Nimblescribe-Releases/releases/latest/download/NimbleScribe.dmg
https://github.com/anikherenow/Nimblescribe-Releases/releases/latest/download/NimbleScribe.msix
```

---

## Step 5 — Update appcast.json

In the `demo-projects` repo, open:

```
nimble-demos/app/nimblescribe/appcast.json/route.ts
```

Update these three fields:

```typescript
const appcast = {
  version: '0.2.1',                                          // ← new version
  url: 'https://nimblescribe.nimblesl.com/download',         // keep as-is
  notes: 'Short description of what changed (1–2 sentences)',// ← new release notes
};
```

Commit, push, and deploy:

```bash
git add .
git commit -m "chore: bump appcast to v0.2.1"
git push
```

Wait for Vercel / your deployment to complete.

---

## Step 6 — Verify end-to-end

### macOS

- [ ] `https://nimblescribe.nimblesl.com/appcast.json` returns `"version": "0.2.1"`
- [ ] `https://nimblescribe.nimblesl.com/download` downloads `NimbleScribe.dmg`
- [ ] DMG opens and installs without Gatekeeper blocking *(notarized)*
- [ ] Launch the **previous** version → update banner appears in Settings → About
- [ ] Click **Update** → browser downloads the new DMG

### Windows

- [ ] `https://github.com/anikherenow/Nimblescribe-Releases/releases/latest/download/NimbleScribe.msix` downloads correctly
- [ ] MSIX installs on a machine with Developer Mode enabled
- [ ] App launches from Start Menu and functions correctly
- [ ] Whisper model downloads and transcription works

---

## Versioning convention

```
MAJOR.MINOR.PATCH+BUILD

0.1.0+1    initial release
0.1.1+2    patch / bug fix
0.2.0+3    new feature(s)
1.0.0+10   first public stable release
```

The `+BUILD` number increments with every build (including failed ones submitted for notarization). It is **never shown to users** — only `MAJOR.MINOR.PATCH` appears in the UI, appcast, and release title.

The four-part MSIX version (`MAJOR.MINOR.PATCH.BUILD`) is derived from the pubspec version automatically by the build script.

---

## Rollback procedure

If a release is broken:

1. **Do not delete the GitHub Release.** A missing release creates broken download links, which is worse than a bad release.
2. Immediately update `appcast.json` to point back to the previous working version string — this prevents existing users from being prompted to "update" to the broken build.
3. Fix the issue in the source repo and ship a new patch release as soon as possible.
4. Once the new release is live, update `appcast.json` to the new version.

---

*Last updated: June 2026*
