<div align="center">

# NimbleScribe

### Press a shortcut. Speak. Text appears at your cursor — instantly.

**100% private · 100% offline · 100% free**

[![Latest Release](https://img.shields.io/github/v/release/anikherenow/Nimblescribe-Releases?style=flat-square&color=A855F7&label=latest%20release)](../../releases/latest)
[![Total Downloads](https://img.shields.io/github/downloads/anikherenow/Nimblescribe-Releases/total?style=flat-square&color=10B981&label=total%20downloads)](../../releases)
[![macOS](https://img.shields.io/badge/macOS-13%2B%20%C2%B7%20Apple%20Silicon-black?style=flat-square&logo=apple)](../../releases/latest/download/NimbleScribe.dmg)
[![Windows](https://img.shields.io/badge/Windows-10%2F11%20%C2%B7%20x64-0078D4?style=flat-square&logo=windows)](../../releases/latest/download/NimbleScribe.msix)

[Website](https://nimblescribe.nimblesl.com) · [Download](#-download) · [What's New](../../releases) · [Docs](https://nimblescribe.nimblesl.com/docs) · [Report a Bug](../../issues)

</div>

---

NimbleScribe is a desktop dictation app that types your spoken words directly at your cursor — in any application, any window, without copy-pasting. Every transcription runs locally on your device using [OpenAI Whisper](https://github.com/openai/whisper). Your voice never touches a server.

No account. No subscription. No telemetry. No catch.

---

## ⬇️ Download

<table>
<tr>
<td align="center" width="50%">

### 🍎 macOS

<a href="https://github.com/anikherenow/Nimblescribe-Releases/releases/latest/download/NimbleScribe.dmg">
  <img src="https://img.shields.io/badge/Download-NimbleScribe.dmg-A855F7?style=for-the-badge&logo=apple" alt="Download for macOS" />
</a>

macOS 13 Ventura or later · Apple Silicon M1–M4

</td>
<td align="center" width="50%">

### 🪟 Windows

<a href="https://github.com/anikherenow/Nimblescribe-Releases/releases/latest/download/NimbleScribe.msix">
  <img src="https://img.shields.io/badge/Download-NimbleScribe.msix-0078D4?style=for-the-badge&logo=windows" alt="Download for Windows" />
</a>

Windows 10 or 11 (x64) · Intel or AMD

</td>
</tr>
</table>

> Or visit **[nimblescribe.nimblesl.com/download](https://nimblescribe.nimblesl.com/download)** for the latest release notes.

---

## ✨ Features

| | Feature | Description |
|---|---|---|
| 🎙️ | **Real-time dictation** | Press a shortcut, speak, release — text appears at your cursor in any app, zero copy-paste |
| 🔒 | **100% private** | Audio is processed entirely on-device. Nothing is ever sent to a server |
| 🌍 | **100+ languages** | Whisper auto-detects and transcribes any language with no configuration |
| 🤖 | **AI grammar cleanup** | On-device model removes filler words, fixes punctuation, and smooths repetitions |
| 🎧 | **Meeting recorder** | Capture system audio from any meeting — no bot, no shared link, no third-party server |
| 💬 | **Local AI assistant** | On-device Qwen2.5 chat with full context of your transcriptions — no API key, no cost |
| 📋 | **Transcription history** | Every session stored locally in a searchable, exportable log |
| ⌨️ | **Custom shortcuts** | Any global hotkey combination, works system-wide even when the app is in the background |
| 🔔 | **Auto update checks** | Checks for new versions every 24 hours — you decide when to install |
| 🆓 | **Free forever** | No freemium tier, no trial, no hidden limits — every feature for every user, always |

---

## 🚀 How it works

```
1.  Hold your shortcut key          (e.g. Right Option)
2.  Speak naturally
3.  Release the key
4.  Text appears at your cursor     ← in Notion, Slack, VS Code, anywhere
```

No switching apps. No clipboard. No waiting. Just speak and continue.

---

## 📦 Release History

| Version | Date | macOS | Windows | Highlights |
|---------|------|-------|---------|------------|
| **v0.3.0** *(latest)* | Jun 2026 | [.dmg](../../releases/latest/download/NimbleScribe.dmg) | [.msix](../../releases/latest/download/NimbleScribe.msix) | Windows launch · CI/CD pipeline |
| v0.2.1 | Jun 2026 | [.dmg](../../releases/download/v0.2.1/NimbleScribe.dmg) | — | Resizable AI sidebar · persistent chat history |
| v0.1.1 | Jun 2026 | [.dmg](../../releases/download/v0.1.1/NimbleScribe.dmg) | — | Bug fixes |
| v0.1.0 | Jun 2026 | [.dmg](../../releases/download/v0.1.0/NimbleScribe.dmg) | — | Initial release |

---

## 💻 System Requirements

### macOS

| | |
|---|---|
| **OS** | macOS 13 Ventura or later · 14 Sonoma and 15 Sequoia fully supported |
| **Chip** | Apple Silicon — M1, M2, M3, M4 (Pro / Max / Ultra all supported) |
| **RAM** | 8 GB minimum · 16 GB recommended when running large model + AI together |
| **Storage** | ~200 MB app · 300 MB – 1.5 GB per Whisper model · ~500 MB AI model |
| **Internet** | Required once for initial model download — fully offline after that |

> **Intel Macs are not supported.** NimbleScribe relies on Core ML and the Apple Neural Engine for real-time inference, which require Apple Silicon.

### Windows

| | |
|---|---|
| **OS** | Windows 10 or Windows 11 (x64) |
| **CPU** | Any modern x64 processor — Intel or AMD |
| **RAM** | 8 GB minimum · 16 GB recommended when running large model + AI together |
| **Storage** | ~200 MB app · 300 MB – 1.5 GB per Whisper model · ~500 MB AI model |
| **Internet** | Required once for initial model download — fully offline after that |
| **Install** | Enable Developer Mode or Sideload apps in Windows Settings before installing the MSIX |

---

## 🛠️ Installation

### macOS

1. [**Download NimbleScribe.dmg**](https://github.com/anikherenow/Nimblescribe-Releases/releases/latest/download/NimbleScribe.dmg)
2. Open the `.dmg` and drag **NimbleScribe** to your **Applications** folder
3. On first launch: right-click → **Open** → **Open** to bypass Gatekeeper
4. Grant **Microphone** and **Accessibility** access when macOS prompts
5. Open **Settings → Models**, download a Whisper model, and start dictating

### Windows

1. [**Download NimbleScribe.msix**](https://github.com/anikherenow/Nimblescribe-Releases/releases/latest/download/NimbleScribe.msix)
2. Enable **Developer Mode**: Windows Settings → System → For Developers → On
   *(alternatively: Settings → Apps → Advanced app settings → Choose where to get apps → Anywhere)*
3. Double-click `NimbleScribe.msix` → click **Install**
4. Launch NimbleScribe from the Start Menu
5. Open **Settings → Models**, download a Whisper model, and start dictating

---

## 🔄 Updates

NimbleScribe checks for updates on every launch and every 24 hours. When a new version is available, a notification appears in **Settings → About**. There are no silent background updates — you always choose when to install.

To update manually: download the latest release from this page and install it over the existing version. Your models, history, and settings are preserved.

---

## ❓ FAQ

<details>
<summary><strong>"Apple cannot check it for malicious software" — app won't open</strong></summary>

Right-click (or Control-click) **NimbleScribe.app** in Applications → **Open** → **Open**. This one-time bypass is required for apps distributed outside the Mac App Store. The app contains no malicious code — all source is compiled from the private NimbleScribe Flutter repository and processed entirely on your machine.

</details>

<details>
<summary><strong>"Windows protected your PC" — installation warning</strong></summary>

NimbleScribe is currently distributed as an unsigned MSIX. Click **More info → Run anyway**. You also need **Developer Mode** enabled in Windows Settings before installing. We are working on obtaining an EV code-signing certificate to remove this requirement in a future release.

</details>

<details>
<summary><strong>Where are my recordings and transcriptions stored?</strong></summary>

Everything is stored locally on your device — nothing is ever uploaded:

- **macOS:** `~/Library/Application Support/com.nimblescribe.app/`
- **Windows:** `%AppData%\com.nimblescribe.app\`

You can export or delete your data at any time from within the app.

</details>

<details>
<summary><strong>Which Whisper model should I start with?</strong></summary>

| Model | Size | Best for |
|-------|------|----------|
| `tiny` | ~150 MB | Ultra-fast, limited accuracy |
| `base` | ~280 MB | Good balance for everyday use |
| `small` | ~460 MB | Better accuracy, still fast |
| `large-v3-turbo` | ~1.5 GB | Best accuracy across all languages — recommended |

You can switch models at any time in **Settings → Models** and delete models you no longer need.

</details>

<details>
<summary><strong>Does the meeting recorder need a bot or account?</strong></summary>

No bot, no account, no link to share. NimbleScribe captures system audio directly:
- **macOS** — uses the Screen Recording permission to tap system audio output
- **Windows** — uses WASAPI loopback capture

Other meeting participants are not notified that you are recording. The recording never leaves your device.

</details>

<details>
<summary><strong>Is the AI assistant really local? No OpenAI API calls?</strong></summary>

Yes, entirely local. The AI assistant runs a quantised [Qwen2.5](https://github.com/QwenLM/Qwen2.5) language model on-device via [llama.cpp](https://github.com/ggml-org/llama.cpp). No API key, no OpenAI billing, no data transmitted. The model (~500 MB) downloads once and runs permanently offline with full context of your transcriptions.

</details>

<details>
<summary><strong>Does it work on Intel Macs?</strong></summary>

No. NimbleScribe uses Apple's Core ML framework and the Neural Engine for real-time inference — both of which are exclusive to Apple Silicon (M1 and later). Running Whisper in real time on Intel hardware would be unusably slow.

</details>

<details>
<summary><strong>Is there a mobile version?</strong></summary>

Not currently. NimbleScribe is a desktop app for macOS and Windows. Mobile requires a different architecture due to OS-level restrictions on microphone access and system-wide text injection. It may be explored in a future version.

</details>

---

## 🔐 Privacy

NimbleScribe is built with a privacy-first architecture — not as a feature, but as a constraint:

| | |
|---|---|
| 🚫 **No account** | No sign-up, no login, no user profile of any kind |
| 🚫 **No telemetry** | Zero usage data, crash reports, or analytics collected |
| 🚫 **No audio transmission** | Your voice is processed on-device and never streamed anywhere |
| 🚫 **No network calls during use** | After the one-time model download, the app makes zero outbound requests |
| ✅ **Local storage only** | All transcriptions, chat history, and settings live exclusively on your device |

---

## 🔗 Links

| | |
|---|---|
| 🌐 **Website** | [nimblescribe.nimblesl.com](https://nimblescribe.nimblesl.com) |
| 📖 **Docs** | [nimblescribe.nimblesl.com/docs](https://nimblescribe.nimblesl.com/docs) |
| 📦 **All releases** | [Releases page](../../releases) |
| 🐛 **Bug reports** | [Open an issue](../../issues) |
| 🏢 **Built by** | [NimbleSL](https://nimblesl.com) — Dhaka, Bangladesh |

---

<div align="center">

**[nimblescribe.nimblesl.com](https://nimblescribe.nimblesl.com)**

Free forever · No data collected · Built by [NimbleSL](https://nimblesl.com)

</div>
