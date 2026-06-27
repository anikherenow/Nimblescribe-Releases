<div align="center">

<img src="https://nimblescribe.nimblesl.com/nimblescribe-icon.png" width="96" height="96" alt="NimbleScribe" />

# NimbleScribe

**Voice-to-text for macOS and Windows. Private, instant, and free — forever.**

[![Latest Release](https://img.shields.io/github/v/release/anikherenow/Nimblescribe-Releases?style=flat-square&color=A855F7&label=latest)](../../releases/latest)
[![Total Downloads](https://img.shields.io/github/downloads/anikherenow/Nimblescribe-Releases/total?style=flat-square&color=10B981&label=downloads)](../../releases)
[![Platform](https://img.shields.io/badge/platform-macOS%20%7C%20Windows-lightgrey?style=flat-square)](../../releases/latest)
[![License](https://img.shields.io/badge/license-free-blue?style=flat-square)](../../releases/latest)

[**nimblescribe.nimblesl.com**](https://nimblescribe.nimblesl.com) · [Download](#download) · [What's New](../../releases) · [Report an Issue](../../issues)

</div>

---

Press a shortcut. Speak. Your words appear at your cursor — in any app, on any window, with zero latency. No account. No subscription. No audio ever sent anywhere.

NimbleScribe runs every transcription locally on your device using [OpenAI Whisper](https://github.com/openai/whisper). What you say never touches a server.

---

## Download

<table>
<tr>
<td align="center" width="50%">

### 🍎 macOS

**[Download NimbleScribe.dmg](https://github.com/anikherenow/Nimblescribe-Releases/releases/latest/download/NimbleScribe.dmg)**

macOS 13 Ventura or later · Apple Silicon (M1–M4)

</td>
<td align="center" width="50%">

### 🪟 Windows

**[Download NimbleScribe.msix](https://github.com/anikherenow/Nimblescribe-Releases/releases/latest/download/NimbleScribe.msix)**

Windows 10 or 11 (x64) · Any modern CPU

</td>
</tr>
</table>

Or visit **[nimblescribe.nimblesl.com/download](https://nimblescribe.nimblesl.com/download)** for the latest release with full release notes.

### Release History

| Version | Date | macOS | Windows | Notes |
|---------|------|-------|---------|-------|
| **v0.2.1** *(latest)* | Jun 2026 | [.dmg](../../releases/latest/download/NimbleScribe.dmg) | [.msix](../../releases/latest/download/NimbleScribe.msix) | Windows support · Resizable AI sidebar |
| v0.1.1 | Jun 2026 | [.dmg](../../releases/download/v0.1.1/NimbleScribe.dmg) | — | Bug fixes |
| v0.1.0 | Jun 2026 | [.dmg](../../releases/download/v0.1.0/NimbleScribe.dmg) | — | Initial release |

---

## What is NimbleScribe?

NimbleScribe is a desktop dictation app that injects transcribed text directly at your cursor in any application — no copy-paste, no switching windows. It is built on top of OpenAI's Whisper model, runs entirely offline, and ships with a local AI assistant powered by a quantised on-device language model.

Everything is processed on your machine. There are no accounts, no telemetry, no usage tracking, and no subscription of any kind.

---

## Features

| | |
|---|---|
| 🎙️ **Real-time dictation** | Press a shortcut, speak, release — text appears at your cursor instantly in any app |
| 🔒 **100% private** | Audio never leaves your device. All transcription runs locally using Whisper |
| 🌍 **100+ languages** | Whisper automatically detects and transcribes any language with no configuration |
| 🤖 **AI Grammar Cleanup** | An on-device model removes filler words, fixes punctuation, and smooths repetitions |
| 📋 **Transcription history** | Every recording is stored locally in a searchable, exportable history log |
| 🎧 **Meeting Recorder** | Record system audio from any meeting app — no bot, no shared links, fully private |
| 💬 **Local AI Assistant** | On-device chat powered by Qwen2.5 — full context of your transcriptions, zero API cost |
| ⌨️ **Custom shortcuts** | Register any global hotkey combination, system-wide, even when the app is in the background |
| 🔔 **Update notifications** | Checks for new versions every 24 hours; you always decide when to update |
| 🆓 **Free forever** | No freemium, no trial, no hidden tiers — every feature, for every user, always |

---

## System Requirements

### macOS

| | |
|---|---|
| **OS** | macOS 13 Ventura or later (14 Sonoma, 15 Sequoia fully supported) |
| **Chip** | Apple Silicon — M1, M2, M3, or M4 (Pro, Max, Ultra variants all supported) |
| **RAM** | 8 GB minimum · 16 GB recommended for large models + AI simultaneously |
| **Storage** | ~200 MB app · 300 MB–1.5 GB per Whisper model · ~500 MB AI assistant model |
| **Internet** | Required once for initial model download — fully offline after that |

> **Intel Macs are not supported.** NimbleScribe uses Core ML and the Neural Engine for real-time inference, which require Apple Silicon.

### Windows

| | |
|---|---|
| **OS** | Windows 10 or Windows 11 (x64) |
| **CPU** | Any modern x64 processor — Intel or AMD |
| **RAM** | 8 GB minimum · 16 GB recommended for large models + AI simultaneously |
| **Storage** | ~200 MB app · 300 MB–1.5 GB per Whisper model · ~500 MB AI assistant model |
| **Internet** | Required once for initial model download — fully offline after that |
| **Install** | Requires Developer Mode or Sideload apps enabled in Windows Settings (unsigned MSIX) |

---

## Installation

### macOS

1. [Download **NimbleScribe.dmg**](https://github.com/anikherenow/Nimblescribe-Releases/releases/latest/download/NimbleScribe.dmg)
2. Open the `.dmg` and drag **NimbleScribe** into your **Applications** folder
3. On first launch, right-click the app → **Open** to bypass Gatekeeper *(the app is unsigned pending notarization)*
4. Grant **Microphone** access when macOS prompts
5. Open **Settings → Models**, download a Whisper model, and start dictating

### Windows

1. [Download **NimbleScribe.msix**](https://github.com/anikherenow/Nimblescribe-Releases/releases/latest/download/NimbleScribe.msix)
2. Before installing, enable **Developer Mode** in Windows Settings → System → For Developers
   *(or go to Settings → Apps → Advanced app settings → Choose where to get apps → Anywhere)*
3. Double-click `NimbleScribe.msix` and click **Install**
4. Launch NimbleScribe from the Start Menu
5. Open **Settings → Models**, download a Whisper model, and start dictating

---

## Updates

NimbleScribe checks for new versions on launch and every 24 hours. When an update is available you will see a notification in **Settings → About**. There is no silent background update — you choose when to install.

To update manually: download the latest release from this page and install it over the existing version.

---

## FAQ

<details>
<summary><strong>"Apple cannot check it for malicious software" — app won't open (macOS)</strong></summary>

Right-click (or Control-click) **NimbleScribe.app** in Applications → **Open** → **Open**. This one-time step is required because the app is currently distributed without an Apple notarization certificate. The app itself contains no malicious code — all source is compiled from the private NimbleScribe Flutter repository.

</details>

<details>
<summary><strong>Windows says the app is from an unknown publisher</strong></summary>

NimbleScribe is currently distributed as an unsigned MSIX. You need to enable **Developer Mode** or **Sideload apps** in Windows Settings before installing. We are working on obtaining an EV code-signing certificate for a future release.

</details>

<details>
<summary><strong>Where are my recordings and transcriptions stored?</strong></summary>

Everything is stored locally on your device:
- **macOS:** `~/Library/Application Support/com.nimblescribe.app/`
- **Windows:** `%AppData%\com.nimblescribe.app\`

Nothing is ever uploaded to any server.

</details>

<details>
<summary><strong>Which Whisper model should I download first?</strong></summary>

- **`base` or `small`** — fast, accurate, good for everyday use
- **`large-v3-turbo`** — best accuracy across all languages, ~1.5 GB, recommended for professionals
- **`tiny`** — ultra-fast, lower accuracy, best if RAM is limited

You can switch models at any time in **Settings → Models** and delete ones you no longer need.

</details>

<details>
<summary><strong>Does it work on Intel Macs?</strong></summary>

No. NimbleScribe uses Apple's Core ML framework and the Neural Engine, which are exclusive to Apple Silicon (M1 and later). Real-time transcription performance on Intel hardware would be unusable.

</details>

<details>
<summary><strong>Does the meeting recorder need a bot to join the call?</strong></summary>

No. NimbleScribe captures system audio directly — no bot, no link to share, no third-party servers involved. On **macOS**, it uses the Screen Recording permission to tap into system audio. On **Windows**, it uses WASAPI loopback capture. Other participants are unaware that you are recording.

</details>

<details>
<summary><strong>Is the AI assistant really local? No OpenAI API key?</strong></summary>

Yes, entirely local. The AI assistant runs a quantised Qwen2.5 language model on-device via llama.cpp. No API key required, no OpenAI billing, no data transmitted. The model file (~500 MB) downloads once and runs offline permanently.

</details>

---

## Privacy

NimbleScribe is designed with a privacy-first architecture:

- **No account required** — there is no sign-up, login, or user profile
- **No telemetry** — we collect zero usage data, crash reports, or analytics
- **No audio transmission** — your voice is processed locally and never streamed anywhere
- **No network calls during use** — after the one-time model download, the app makes zero outbound requests
- **Local storage only** — transcriptions, chat history, and settings live exclusively on your device

---

## Links

| | |
|---|---|
| 🌐 **Website** | [nimblescribe.nimblesl.com](https://nimblescribe.nimblesl.com) |
| 📖 **Documentation** | [nimblescribe.nimblesl.com/docs](https://nimblescribe.nimblesl.com/docs) |
| 🏢 **Built by** | [NimbleSL](https://nimblesl.com) |
| 🐛 **Bug reports** | [Open an issue](../../issues) |
| 📦 **All releases** | [Releases page](../../releases) |

---

<div align="center">

Made with care by [NimbleSL](https://nimblesl.com) · Free forever · No data collected

</div>
