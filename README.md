<div align="center">

<br/>

```
 ██████╗ ██████╗ ████████╗██╗███╗   ███╗
██╔═══██╗██╔══██╗╚══██╔══╝██║████╗ ████║
██║   ██║██████╔╝   ██║   ██║██╔████╔██║
██║   ██║██╔═══╝    ██║   ██║██║╚██╔╝██║
╚██████╔╝██║        ██║   ██║██║ ╚═╝ ██║
 ╚═════╝ ╚═╝        ╚═╝   ╚═╝╚═╝     ╚═╝
```

### Image Optimizer — Fast. Private. Client-side. Zero dependencies.

<br/>

[![Version](https://img.shields.io/badge/version-1.0.0-c8ff00?style=for-the-badge)](https://github.com/fartektv/web.optim/releases)
[![License](https://img.shields.io/badge/license-Apache%202.0-ff6b35?style=for-the-badge)](https://www.apache.org/licenses/LICENSE-2.0)
[![Built With](https://img.shields.io/badge/built_with-HTML%20·%20CSS%20·%20JS-3dffa0?style=for-the-badge)]()
[![Zero Dependencies](https://img.shields.io/badge/dependencies-zero-c8ff00?style=for-the-badge)]()
[![Privacy](https://img.shields.io/badge/privacy-100%25%20local-3dffa0?style=for-the-badge)]()
[![PWA](https://img.shields.io/badge/works-offline-ff6b35?style=for-the-badge)]()

<br/>

> **OPTIM** is a professional-grade image optimizer that runs entirely in your browser.  
> No server. No upload. No account. No data collection. Just results.

<br/>

[🚀 Open App](https://fartektv.github.io/web.optim/) · [📖 Documentation](#-documentation) · [🐛 Report a Bug](../../issues) · [💡 Request a Feature](../../issues)

<br/>

---

</div>

## 📋 Table of Contents

- [Why OPTIM?](#-why-optim)
- [Features](#-features)
- [Getting Started](#-getting-started)
- [How It Works](#-how-it-works)
- [Tech Stack](#-tech-stack)
- [Browser Compatibility](#-browser-compatibility)
- [Privacy](#-privacy)
- [Project Structure](#-project-structure)
- [License](#-license)

---

## 💡 Why OPTIM?

Most image optimization tools require you to upload your files to a third-party server — exposing your images to unknown infrastructure, raising privacy concerns, and introducing latency. **OPTIM eliminates all of that.**

Everything happens directly inside your browser using the native Canvas API. Your images never leave your device. Period.

| | OPTIM | Online tools | Desktop apps |
|---|:---:|:---:|:---:|
| No upload required | ✅ | ❌ | ✅ |
| No installation | ✅ | ✅ | ❌ |
| Works offline | ✅ | ❌ | ✅ |
| Zero dependencies | ✅ | — | — |
| Free forever | ✅ | ⚠️ | ⚠️ |
| Privacy guaranteed | ✅ | ❌ | ⚠️ |

---

## ✨ Features

### 🖼️ Input & Preview
- **Drag & drop** or click-to-browse file selection
- Supported formats: **JPG · PNG · WebP · BMP · TIFF**
- Instant preview on load — no processing delay
- Three preview modes:
  - `Original` — raw input image
  - `Optimized` — processed output
  - `Compare ↔` — interactive drag slider for before/after

### 📦 Output Formats
| Format | Best for |
|---|---|
| **JPG** | Photos, complex scenes, wide compatibility |
| **WebP** | Modern web, best size-to-quality ratio |
| **PNG** | Transparency, lossless graphics, screenshots |

> Automatic format suggestion based on the input file type.

### ⚙️ Compression Engine

Quality slider from **1 → 100** with contextual labels:

```
1 ──── 25 ──── 50 ──── 75 ──── 100
Low   Medium  Standard  High   Max
```

Four compression methods:

| Method | Description |
|---|---|
| **Auto** | Recommended balanced mode — best for most use cases |
| **Aggressive** | Maximum file size reduction — may reduce quality |
| **Lossless** | Zero quality loss — larger output file |
| **Balanced** | Slight quality trade-off for significantly better size |

### 📐 Resize & Dimension Control
- Enable/disable resize independently from compression
- Manual **width × height** inputs with live feedback
- **Aspect ratio lock** — maintains proportions automatically
- Resize algorithm selector:
  - `Bicubic` — smooth, professional-grade scaling
  - `High Quality Smooth` — anti-aliased output
  - `Pixelated` — crisp edges for pixel art / icons

Quick presets for common targets:

```
[ 1080p ] [ 720p ] [ 800px ] [ 400px ] [ Thumbnail ] [ ×½ ]
```

### 🎨 Image Adjustments
All adjustments are applied via direct pixel manipulation — no filters, no approximations:

| Control | Method |
|---|---|
| **Sharpness** | Convolution kernel sharpening |
| **Brightness** | Per-channel pixel-level offset |
| **Contrast** | Histogram stretching |
| **Saturation** | Per-channel desaturation blend |

### 🔧 Advanced Options

| Option | Effect |
|---|---|
| **Strip EXIF metadata** | Removes GPS coordinates, device model, timestamps |
| **Progressive JPEG** | Enables progressive loading for web delivery |
| **White background fill** | Replaces transparency when exporting PNG → JPG |

### 📊 Live Stats & Histogram
- Side-by-side file size comparison (original vs. optimized)
- **Savings percentage** displayed in real time
- Output dimensions confirmation
- **RGB histogram** updated live as you adjust settings

---

## 🚀 Getting Started

No build step. No npm. No configuration. No dependencies.

### Option 1 — Use the live app (instant)
```
https://fartektv.github.io/web.optim/
```

### Option 2 — Run locally
```bash
# Clone the repository
git clone https://github.com/fartektv/web.optim.git

# Navigate into the project
cd web.optim

# Open in your browser (no server needed)
open index.html
# or on Linux:
xdg-open index.html
# or on Windows:
start index.html
```

### Option 3 — Local HTTP server (optional)
```bash
# Python 3
python3 -m http.server 8080

# Node.js
npx serve .

# PHP
php -S localhost:8080
```
Then visit `http://localhost:8080`.

---

## 🔬 How It Works

OPTIM uses the browser's native **HTML5 Canvas API** to perform all image operations client-side:

```
┌─────────────┐     ┌──────────────────┐     ┌─────────────────────┐
│  Input file  │────▶│  FileReader API  │────▶│  HTMLImageElement   │
│ (JPG/PNG/…) │     │  (local read)    │     │  (decode to bitmap) │
└─────────────┘     └──────────────────┘     └──────────┬──────────┘
                                                         │
                    ┌────────────────────────────────────▼──────────┐
                    │           OffscreenCanvas / Canvas 2D          │
                    │  ┌──────────┐  ┌────────────┐  ┌───────────┐  │
                    │  │  Resize  │  │  Adjustments│  │  Compress │  │
                    │  │ algorithm│  │ (pixel ops) │  │  (toBlob) │  │
                    │  └──────────┘  └────────────┘  └───────────┘  │
                    └────────────────────────────┬───────────────────┘
                                                 │
                              ┌──────────────────▼────────────────┐
                              │         Output Blob (download)     │
                              │     JPG · WebP · PNG + stats       │
                              └───────────────────────────────────┘
```

**No pixel of your image ever leaves your machine.**

---

## 🧱 Tech Stack

| Technology | Role |
|---|---|
| **HTML5 Canvas API** | Image rendering, pixel manipulation, compositing |
| **`canvas.toBlob()`** | Client-side compression & format encoding |
| **FileReader API** | Local file reading without server upload |
| **CSS Custom Properties** | Design system & theming |
| **Google Fonts** | Typography — Syne (display) + Space Mono (mono) |

Zero runtime dependencies. Zero build tools. One HTML file.

---

## 🌐 Browser Compatibility

| Browser | Version | Status |
|---|---|---|
| Chrome / Chromium | 80+ | ✅ Full support |
| Edge | 80+ | ✅ Full support |
| Firefox | 75+ | ✅ Full support |
| Safari | 14+ | ✅ Full support |
| iOS Safari | 14+ | ✅ Touch-enabled |
| Android Chrome | 80+ | ✅ Touch-enabled |

> ⚠️ **WebP export** is not supported on Safari versions older than 14.  
> PNG and JPG export work on all browsers listed above.

---

## 🔒 Privacy

OPTIM was designed with a **privacy-first** philosophy from the ground up.

- 🔐 **No upload** — images are never sent to any server
- 📡 **No analytics** — no tracking pixels, no session recording, no telemetry
- 🍪 **No cookies** — nothing is stored outside your local session
- 🌐 **Works fully offline** — after the initial page load, no network required
- 🧹 **EXIF stripping** — optionally removes all embedded metadata before export

All processing is handled by the [Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API) — a sandboxed, read-only browser API. Your images are processed in memory and immediately discarded when you close the tab.

---

## 📁 Project Structure

```
web.optim/
├── index.html    ← Entire application (HTML + CSS + JS, self-contained)
└── README.md     ← This file
```

OPTIM is intentionally a single-file application — making it trivially easy to self-host, fork, audit, or embed.

---

## 🛠️ Contributing

Contributions, bug reports, and feature requests are welcome.

```bash
# Fork the repo on GitHub, then:
git checkout -b feature/your-feature-name
git commit -m "feat: describe your change"
git push origin feature/your-feature-name
# Open a Pull Request
```

Please follow [Conventional Commits](https://www.conventionalcommits.org/) for commit messages:

| Prefix | Use for |
|---|---|
| `feat:` | New feature |
| `fix:` | Bug fix |
| `perf:` | Performance improvement |
| `style:` | CSS / visual change |
| `docs:` | Documentation update |
| `refactor:` | Code restructuring |

---

## 📄 License

Licensed under the **Apache License, Version 2.0**.

```
Copyright 2025 Rafael ISTE — FarTekTV

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at:

    https://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```

---

<div align="center">

<br/>

**© 2025 Rafael ISTE — FarTekTV. All rights reserved.**

<br/>

[![FarTekTV](https://img.shields.io/badge/FarTekTV-YouTube-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://youtube.com/@FarTekTV)
[![WebMake Studio](https://img.shields.io/badge/WebMake_Studio-Portfolio-c8ff00?style=for-the-badge&logoColor=black)](https://webmake-studio.netlify.app/)
[![GitHub](https://img.shields.io/badge/FarTekTV-GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/fartektv)

<br/>

*Built with ⚡ by [WebMake Studio](https://webmake-studio.netlify.app/) × FarTekTV*

<br/>

</div>
