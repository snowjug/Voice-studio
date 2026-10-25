<div align="center">
  <img src="docs/logo.png" alt="VoiceStudio" width="100" />
  <h1>🎙️ VoiceStudio</h1>
  <p><strong>Open-source, local-first voice cloning, voice design, video dubbing, dictation, transcription &amp; audiobook creation in 646 languages.</strong></p>
  <p>
    <img src="https://img.shields.io/badge/version-0.5.7--beta.2-blueviolet?style=flat-square" alt="Version" />
    <img src="https://img.shields.io/badge/license-AGPL--3.0-blue?style=flat-square" alt="AGPL-3.0" />
    <img src="https://img.shields.io/badge/languages-646-green?style=flat-square" alt="Languages" />
    <img src="https://img.shields.io/badge/platform-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey?style=flat-square" alt="Platform" />
    <img src="https://img.shields.io/badge/Python-3.11%2B-yellow?style=flat-square" alt="Python" />
    <img src="https://img.shields.io/badge/Node.js-22%2B-brightgreen?style=flat-square" alt="Node.js" />
  </p>
  <p>
    <a href="https://voicestudio.sh">Website</a> ·
    <a href="https://github.com/snowjug/Voice-studio/releases/latest">Download</a> ·
    <a href="#-get-started">Get Started</a> ·
    <a href="#-documentation">Docs</a> ·
    <a href="https://discord.gg/bzQavDfVV9">Discord</a>
  </p>
</div>

---

> **VoiceStudio** is a privacy-first, cross-platform desktop application that puts professional-grade voice AI directly on your hardware — no cloud required. Clone voices, dub videos, design new voices, transcribe audio, and produce audiobooks — all locally.

---

## ✨ Features

| 🎤 Create | 🎬 Produce | 🔌 Connect |
| :--- | :--- | :--- |
| Clone any voice with a short sample | Dub videos with timed speech in 646 languages | Local REST API for agent integration |
| Design voices from a text description | Generate stories, audiobooks & batch jobs | MCP (Model Context Protocol) server |
| Real-time dictation with floating widget | Watch folders for automated pipelines | Reusable recipes for repeated workflows |

### 🚀 Highlights

- **646 languages** — Multilingual TTS powered by OmniVoice and a pluggable engine catalog
- **Zero-shot voice cloning** — Clone any voice from a short, clean reference audio clip
- **Video dubbing** — Auto-align dubbed speech to video timing
- **Audiobook production** — Multi-chapter, multi-voice narration with batch processing
- **Local API & MCP** — Integrate with AI agents, Cursor, Claude Code, and more
- **Privacy first** — All processing runs on your hardware; remote services are optional
- **Cross-platform** — macOS (Apple Silicon + Intel UI), Windows, Linux, Docker

---

## 🖥️ Screenshots

<details>
<summary><strong>📸 Explore the workspaces</strong> · Clone, dub, design & models</summary>

<table>
  <tr>
    <td><img src="docs/media/electron/voice-cloning.png" alt="Voice cloning workspace" width="100%" /></td>
    <td><img src="docs/media/electron/dubbing.png" alt="Video dubbing workspace" width="100%" /></td>
  </tr>
  <tr><td align="center">Voice cloning</td><td align="center">Video dubbing</td></tr>
  <tr>
    <td><img src="docs/media/electron/voice-design.png" alt="Voice design workspace" width="100%" /></td>
    <td><img src="docs/media/electron/models.png" alt="Model manager" width="100%" /></td>
  </tr>
  <tr><td align="center">Voice design</td><td align="center">Local model manager</td></tr>
</table>

<img width="2628" height="1950" alt="VoiceStudio desktop workspace" src="https://github.com/user-attachments/assets/b474497d-a453-49a3-a2dd-f023ec6b7659" />

</details>

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Desktop Shell** | [Electron](https://www.electronjs.org/) (v22+) |
| **Frontend** | TypeScript, React, Vite |
| **Backend / AI** | Python 3.11+, PyTorch, Transformers |
| **Speech Engine** | OmniVoice (default) + pluggable engine catalog |
| **Package Manager** | [Bun](https://bun.sh/) 1.4+ |
| **Monorepo** | Turborepo |
| **Database** | SQLite via Alembic migrations |
| **GPU Acceleration** | CUDA (NVIDIA), Metal/MPS (Apple Silicon) |
| **Protocol** | Local REST API + MCP server |

---

## 💻 Hardware Requirements

| Hardware | Support |
|---|---|
| NVIDIA GPU (Windows / Linux) | ✅ Full — CUDA acceleration |
| Apple Silicon (M1/M2/M3/M4) | ✅ Full — Metal (MPS) acceleration |
| CPU only (Intel/AMD integrated) | ✅ Usable — slower; ~5 GB free disk for CPU PyTorch |
| Windows on ARM (Snapdragon X) | ⚠️ Experimental — native ARM64 app, x64 Python under emulation, CPU only |
| Intel Mac | ℹ️ App UI only — connect to a remote backend |

---

## 🚀 Get Started

### One-command install

**macOS / Linux:**
```sh
# Install latest Electron release
curl -fsSL https://voicestudio.sh/install | sh

# Install a specific version (replace X.Y.Z)
curl -fsSL https://voicestudio.sh/install | sh -s -- --version X.Y.Z

# Build from main branch and install
curl -fsSL https://voicestudio.sh/install | sh -s -- --main

# Uninstall (keeps your data)
curl -fsSL https://voicestudio.sh/install | sh -s -- --uninstall
```

**Windows (PowerShell):**
```powershell
irm https://voicestudio.sh/install | iex
```

### Download a release

Get the latest from [Releases](https://github.com/snowjug/Voice-studio/releases/latest):

- 🍎 macOS — .dmg
- 🪟 Windows — .exe
- 🐧 Linux — .AppImage or .deb

Platform guides: **[macOS](docs/install/macos.md) · [Windows](docs/install/windows.md) · [Linux](docs/install/linux.md) · [Docker](docs/install/docker.md)**

### Build from source

**Prerequisites:** Git, Node.js 22+, [Bun](https://bun.sh/), Python 3.11+, Rust/Cargo

```bash
# 1. Clone the repository
git clone https://github.com/snowjug/Voice-studio.git
cd Voice-studio

# 2. Install JavaScript dependencies
bun install

# 3. Set up Python backend (creates venv, installs PyTorch + deps)
bun run setup:api

# 4. Launch the desktop app in development mode
bun run dev
```

Use un run smoke-test to build and launch an isolated packaged Electron app.

> ⚠️ **Note:** Electron is the only desktop app and web UI. Version 0.5.3 was the final Tauri release.

---

## 📁 Project Structure

```
Voice-studio/
├── electron/          # Electron desktop shell (TypeScript/React frontend)
├── backend/           # Python AI backend (FastAPI + PyTorch)
├── omnivoice/         # Bundled OmniVoice TTS engine
├── omnivoice-gallery/ # Voice gallery assets
├── frontend/          # Shared web frontend components
├── mobile/            # iOS & Android preview apps
├── native/            # Native platform integrations
├── scripts/           # Build, install & utility scripts
├── config/            # App configuration
├── deploy/            # Deployment configs (Docker, etc.)
├── docs/              # Full documentation
├── examples/          # API usage examples
├── tests/             # Test suites
└── notebooks/         # Jupyter notebooks for model experimentation
```

---

## 📖 Documentation

| Topic | Link |
|---|---|
| Setup & troubleshooting | [Troubleshooting](docs/install/troubleshooting.md) · [Model downloads](docs/downloading-models.md) |
| Speech engines & quality | [Engine guides](docs/engines/README.md) · [Benchmarks](docs/benchmarks.md) |
| Integrations & API | [Local API](docs/speech-platform.md) · [MCP](docs/mcp.md) · [Examples](examples/README.md) |
| Mobile apps (offline) | [iOS & Android](docs/mobile.md) |
| Development | [Contributing](.github/CONTRIBUTING.md) · [Electron setup](electron/README.md) · [Changelog](CHANGELOG.md) |

---

## 🔌 API & MCP Integration

VoiceStudio exposes a local REST API and MCP server for AI agents and automation:

```python
import requests

# Generate speech via local API
response = requests.post("http://localhost:8000/tts", json={
    "text": "Hello, this is VoiceStudio speaking!",
    "voice_id": "my-cloned-voice",
    "language": "en"
})

with open("output.wav", "wb") as f:
    f.write(response.content)
```

See [Local API docs](docs/speech-platform.md) and [MCP integration](docs/mcp.md).

---

## 🤝 Contributing

Contributions are welcome! Read the [Contributing Guide](.github/CONTRIBUTING.md) before submitting a PR.

```bash
bun run test       # Run tests
bun run typecheck  # Type-check
bun run lint       # Lint
bun run format     # Format code
```

---

## 💖 Sponsors

[GitHub Sponsors](https://github.com/sponsors/debpalash) · [Ko-fi](https://ko-fi.com/debpalash) · [PayPal](https://paypal.me/palashCoder) · [Tiers & recognition](SPONSORS.md)

---

## 📄 License & Responsible Use

Licensed under **[AGPL-3.0](LICENSE)**.

> ⚠️ **Ethical use:** Clone voices **only with explicit permission** from the voice owner.

A commercial licence without AGPL obligations is available — contact **hi@voicestudio.sh**.

---

<div align="center">
  <sub>Built with ❤️ by the VoiceStudio community · <a href="https://voicestudio.sh">voicestudio.sh</a></sub>
</div>
