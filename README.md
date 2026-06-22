# NimbleScribe

> Voice-to-text for macOS. Private, instant, and free.

[![Latest Release](https://img.shields.io/github/v/release/anikherenow/Nimblescribe-Releases)](../../releases/latest)
[![Platform](https://img.shields.io/badge/platform-macOS%2013%2B-lightgrey)](../../releases/latest)
[![Downloads](https://img.shields.io/github/downloads/anikherenow/Nimblescribe-Releases/total)](../../releases)

Press a shortcut. Speak. Your words appear at your cursor — in any app on your Mac. No account, no subscription, no audio sent anywhere.

---

## Download

**[→ nimblescribe.nimblesl.com/download](https://nimblescribe.nimblesl.com/download)**

| Version | Released | Download |
|---------|----------|----------|
| **v0.1.1** *(latest)* | Jun 2026 | [NimbleScribe.dmg](../../releases/download/v0.1.1/NimbleScribe.dmg) |
| v0.1.0 | Jun 2026 | [NimbleScribe.dmg](../../releases/download/v0.1.0/NimbleScribe-0.1.0.dmg) |

---

## Features

- **Fully private** — all transcription runs on your Mac by default; audio never leaves your device
- **Instant results** — sub-second transcription on Apple Silicon
- **100+ languages** — automatically transcribes any language, no configuration needed
- **Works everywhere** — pastes directly at your cursor in any app: Slack, Mail, Notion, your browser
- **AI Cleanup** — automatically fixes punctuation, capitalisation, and filler words after transcription
- **Transcription history** — searchable log of every recording, stored locally on your Mac
- **Meeting mode** — longer recording sessions with structured, timestamped output
- **Local and cloud models** — use on-device Whisper models for full privacy, or connect a cloud transcription API for higher accuracy *(cloud model support coming soon)*
- **Auto-update notifications** — checks for new versions every 24 hours; no silent auto-installs

---

## Requirements

| | |
|---|---|
| **macOS** | 13 Ventura or later |
| **Chip** | Apple Silicon — M1, M2, M3, M4 |
| **Storage** | ~200 MB for the app · 300 MB–1.5 GB for Whisper model files |
| **Internet** | Only needed to download models — fully offline after that |

---

## Installation

1. [Download **NimbleScribe.dmg**](https://nimblescribe.nimblesl.com/download)
2. Open the `.dmg` and drag **NimbleScribe** into **Applications**
3. On first launch, right-click the app → **Open** to bypass Gatekeeper *(app is not yet notarized)*
4. Grant microphone access when prompted
5. Open **Settings → Models**, download a Whisper model, and you're ready

---

## Updates

NimbleScribe checks for new versions on launch and every 24 hours. When an update is available, a prompt appears in **Settings → About** with a direct download link. There is no silent auto-install — you decide when to update.

---

## FAQ

**"Apple cannot check it for malicious software" / app won't open**
Right-click (or Control-click) **NimbleScribe.app** in Applications → **Open** → **Open**. This is a one-time step required because the app is not yet notarized with Apple.

**Where are my recordings and transcriptions stored?**
Everything is stored locally in your Mac's Application Support folder. Nothing is uploaded to any server.

**Which Whisper model should I download first?**
Start with `base` or `small` — fast and accurate for most use cases. Use `large-v3` when you need maximum accuracy and speed is less important.

**Does it work on Intel Macs?**
Not currently. NimbleScribe requires Apple Silicon (M1 or later).

---

## Links

| | |
|---|---|
| **Website** | [nimblescribe.nimblesl.com](https://nimblescribe.nimblesl.com) |
| **Built by** | [NimbleSL](https://nimblesl.com) |
| **Issues / Feedback** | [Open an issue](../../issues) |

---

*Maintainers: see [RELEASING.md](./RELEASING.md) for the step-by-step release process.*
