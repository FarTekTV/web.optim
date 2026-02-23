# OPTIM. — Image Optimizer

> A fast, modern, client-side image optimizer. No server, no upload, no data collection — everything runs directly in your browser.

![Version](https://img.shields.io/badge/version-1.0.0-c8ff00?style=flat-square)
![License](https://img.shields.io/badge/license-Apache%202.0-c8ff00?style=flat-square)
![HTML](https://img.shields.io/badge/built_with-HTML%20%2F%20CSS%20%2F%20JS-ff6b35?style=flat-square)
![No dependencies](https://img.shields.io/badge/dependencies-none-3dffa0?style=flat-square)

---

## ✨ Features

### 🖼️ Input
- Drag & drop or file browser
- Supports **JPG, PNG, WebP, BMP, TIFF**
- Instant preview on load

### 📦 Output formats
- Export as **JPG**, **WebP**, or **PNG**
- Automatic format detection based on input file

### ⚙️ Compression
- Quality slider from **1 to 100** with live label (Low / Medium / Standard / High / Max)
- 4 compression methods:
  - **Auto** — recommended balanced mode
  - **Aggressive** — maximum file size reduction
  - **Lossless** — no quality loss
  - **Balanced** — slight quality reduction for better size

### 📐 Resize
- Enable/disable resize independently
- Manual **width & height** inputs
- **Aspect ratio lock** to keep proportions
- Resize algorithm selector: Bicubic, High quality smooth, Pixelated (pixel art)
- Quick presets: `1080p`, `720p`, `800px`, `400px`, `Thumbnail`, `×½`

### 🎨 Image adjustments
- **Sharpness** — convolution kernel sharpening
- **Brightness** — pixel-level adjustment
- **Contrast** — histogram stretching
- **Saturation** — per-channel desaturation blend

### 🔧 Advanced options
| Option | Description |
|---|---|
| Strip EXIF metadata | Removes GPS, device, date info |
| Progressive JPEG | Enables progressive loading |
| White background | Fills transparency for PNG→JPG export |

### 👁️ Preview modes
- **Original** — raw input image
- **Optimized** — processed output
- **Compare ↔** — interactive drag slider to compare before/after

### 📊 Stats & histogram
- Live file size comparison (original vs optimized)
- Savings percentage
- Output dimensions
- RGB histogram updated in real time

---

## 🚀 Getting started

No build step, no npm, no dependencies. Just open the file.

```bash
git clone https://github.com/fartektv/web.optim
cd optim
open index.html
```

Or simply [download the HTML file](./index.html) and open it in any modern browser.

---

## 🔒 Privacy

All image processing happens **100% locally** in your browser using the [Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API).

- ✅ No image is ever uploaded to a server
- ✅ No analytics, no tracking, no cookies
- ✅ Works fully offline

---

## 🧱 Tech stack

| Technology | Usage |
|---|---|
| HTML5 Canvas API | Image rendering & pixel manipulation |
| `canvas.toBlob()` | Client-side compression & encoding |
| FileReader API | Local file reading |
| CSS custom properties | Theming & design system |
| Google Fonts (Syne + Space Mono) | Typography |

---

## 🌐 Browser compatibility

| Browser | Support |
|---|---|
| Chrome / Edge | ✅ Full |
| Firefox | ✅ Full |
| Safari | ✅ Full |
| Mobile (iOS/Android) | ✅ Touch-enabled |

> WebP export may not be supported on very old Safari versions.

---

## 📁 Project structure

```
optim/
└── index.html   # Single self-contained file (HTML + CSS + JS)
└── README.md
```

---

## 📄 License

Licensed under the **Apache License, Version 2.0**.
You may not use this file except in compliance with the License.
A copy of the License is available at:

> https://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an **"AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND**, either express or implied.

---

<p align="center">Built with ⚡ by <a href="https://webmake-studio.netlify.app/">WebMake Studio, FarTekTV</a></p>
