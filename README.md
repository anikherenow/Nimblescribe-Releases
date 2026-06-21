# NimbleScribe Releases

> Free, offline, on-device voice transcription for macOS.
> Built by [NimbleSL](https://nimblesl.com) · [nimblescribe.nimblesl.com](https://nimblescribe.nimblesl.com)

---

## What this repo is

This is the **public distribution repo** for NimbleScribe release binaries.

It exists for one reason: GitHub Release assets must live on a **public** repository to be downloadable without authentication. The app source code lives in a separate private repo.

**This repo never contains source code.** It only holds:
- Git tags (`v0.1.0`, `v0.2.0`, …)
- `.dmg` binaries attached as GitHub Release assets

The `.dmg` is never committed to git — binaries are attached to Releases only, so this repo stays tiny.

---

## Download

| Version | Date | macOS | Download |
|---------|------|-------|----------|
| **v0.1.0** | Jun 2026 | 13 Ventura+ (Apple Silicon) | [NimbleScribe.dmg](https://github.com/anikherenow/Nimblescribe-Releases/releases/download/v0.1.0/NimbleScribe.dmg) |

> The latest version is always available at:
> **[nimblescribe.nimblesl.com/download](https://nimblescribe.nimblesl.com/download)**

---

## System Requirements

| | |
|---|---|
| **macOS** | 13 Ventura or later |
| **Chip** | Apple Silicon (M1, M2, M3, M4) |
| **Disk space** | ~200 MB for the app + 300 MB – 1.5 GB for model files |
| **Internet** | Only needed to download transcription models — runs fully offline after that |

---

## Installation

1. Download **NimbleScribe.dmg** from the [latest Release](../../releases/latest)
2. Open the `.dmg` and drag **NimbleScribe.app** to your **Applications** folder
3. Launch NimbleScribe — on first open macOS may ask you to confirm; click **Open**
4. Grant microphone access when prompted, then download a transcription model from Settings
5. Press your configured shortcut from anywhere to start recording

---

## In-App Update Notifications

NimbleScribe checks for updates automatically on launch and every 24 hours. When a newer version is available you will see a banner in **Settings → About** with a direct download link. There is no auto-install — you decide when to update.

---

## Links

| | |
|---|---|
| **Website** | [nimblescribe.nimblesl.com](https://nimblescribe.nimblesl.com) |
| **Built by** | [NimbleSL](https://nimblesl.com) |
| **Issues / Feedback** | [Open a GitHub Issue](../../issues) |

---

*Maintainers: see [RELEASING.md](./RELEASING.md) for the step-by-step release process.*
