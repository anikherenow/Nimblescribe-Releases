# NimbleScribe — Release Checklist

Step-by-step process for shipping a new version of NimbleScribe.

---

## DMG naming rule — READ FIRST

> **The DMG asset MUST always be named exactly `NimbleScribe.dmg` — no version number in the filename.**

This is what makes `/download` work as a permanent one-click link:
```
https://github.com/anikherenow/Nimblescribe-Releases/releases/latest/download/NimbleScribe.dmg
```
GitHub's `/releases/latest/download/<name>` always resolves to the newest release's asset with that exact name. If you add a version number to the filename (e.g. `NimbleScribe-0.2.0.dmg`), the one-click download breaks.

---

## Prerequisites (one-time setup)

- [ ] Apple Developer Program membership (for signing + notarization)
- [ ] Developer ID Application certificate installed in Keychain
- [ ] `xcrun notarytool` credentials stored (`--keychain-profile nimblescribe`)
- [ ] `create-dmg` installed: `brew install create-dmg`
- [ ] This repo cloned locally and pushed to GitHub as a **public** repo

---

## Release Steps

### 1 — Bump the version

In the Flutter project (`NimbleScribe/`):

```yaml
# pubspec.yaml
version: 0.2.0+2   # format: MAJOR.MINOR.PATCH+BUILD_NUMBER
```

Commit and push to the private source repo.

---

### 2 — Build the macOS app

```bash
cd /path/to/NimbleScribe
flutter build macos --release
```

Output: `build/macos/Build/Products/Release/NimbleScribe.app`

---

### 3 — Create the DMG

⚠️ **Name the output file `NimbleScribe.dmg` — no version number.**

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

---

### 4 — Sign the DMG

```bash
codesign --sign "Developer ID Application: YOUR NAME (TEAM_ID)" \
         --verbose \
         "NimbleScribe.dmg"
```

---

### 5 — Notarize with Apple

```bash
xcrun notarytool submit "NimbleScribe.dmg" \
  --keychain-profile "nimblescribe" \
  --wait
```

Wait for `status: Accepted`. Then staple:

```bash
xcrun stapler staple "NimbleScribe.dmg"
```

Verify:
```bash
spctl --assess --type open --context context:primary-signature "NimbleScribe.dmg"
# Expected: "accepted"
```

---

### 6 — Create a GitHub Release

1. Go to this repo on GitHub → **Releases → Draft a new release**
2. Tag: `v0.2.0`
3. Title: `NimbleScribe 0.2.0`
4. Write release notes (1–2 sentences — shown in the in-app update banner)
5. Attach **`NimbleScribe.dmg`** as a binary asset ← exact filename, no version suffix
6. Publish the release

The permanent download URL will be:
```
https://github.com/anikherenow/Nimblescribe-Releases/releases/latest/download/NimbleScribe.dmg
```

---

### 7 — Update appcast.json

In the `demo-projects` repo, edit:

```
nimble-demos/app/nimblescribe/appcast.json/route.ts
```

Update these three values:

```typescript
const appcast = {
  version: '0.2.0',                                        // ← new version
  url: 'https://nimblescribe.nimblesl.com/download',       // keep as-is (redirects to dmg)
  notes: 'What changed in this version (1-2 sentences)',   // ← new release notes
};
```

Commit, push, and deploy `demo-projects`.

---

### 8 — Verify end-to-end

- [ ] `https://nimblescribe.nimblesl.com/appcast.json` returns the new version
- [ ] `https://nimblescribe.nimblesl.com/download` downloads `NimbleScribe.dmg` directly
- [ ] Download and install the `.dmg` on a clean Mac — Gatekeeper approves it
- [ ] Launch the previous version of the app — update banner appears in Settings → About
- [ ] Click **Update** → browser opens and downloads the new `.dmg`

---

## Version numbering convention

```
MAJOR.MINOR.PATCH+BUILD

0.1.0+1   — initial release
0.1.1+2   — bug fix
0.2.0+3   — new features
1.0.0+10  — first stable / public launch
```

The `+BUILD` number increments with every build submitted for notarization. It is **not** shown to users — only `MAJOR.MINOR.PATCH` is shown in the UI and appcast.

---

## Rollback

If a release is bad:
1. **Do not delete the GitHub Release** — broken download links are worse than a bad release
2. Update `appcast.json` to point back to the previous working version + `.dmg` URL
3. Publish a new patch release as soon as the fix is ready

---

*Last updated: June 2026*
