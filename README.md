# 🔒 Private File Converter

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![GitHub Pages](https://img.shields.io/badge/Live-GitHub%20Pages-brightgreen)](https://purpledoubled.github.io/file-converter/)
[![No Server](https://img.shields.io/badge/Server-None-red)](https://purpledoubled.github.io/file-converter/)

**Convert files directly in your browser. Nothing gets uploaded. Ever.**

🌐 **[Use it now →](https://purpledoubled.github.io/file-converter/)**

## ⚠️ Why This Exists

The FBI [warned](https://www.ic3.gov/PSA/2025/PSA250313) about malicious online file converters stealing personal data and installing malware. Most converter sites upload your files to their servers — you have no idea what happens to them.

**This converter processes everything locally.** Your files never leave your browser. No uploads, no server, no risk.

## 🔄 Supported Conversions

| From | To |
|------|-----|
| JPG | PNG, WebP, PDF |
| PNG | JPG, WebP, PDF |
| WebP | PNG, JPG, PDF |
| PDF | PNG, JPG |
| HEIC/HEIF (iPhone) | JPG |
| SVG | PNG, JPG |

### Dedicated Guides
- [HEIC to JPG](https://purpledoubled.github.io/file-converter/heic-to-jpg.html) — Convert iPhone photos
- [PDF to PNG](https://purpledoubled.github.io/file-converter/pdf-to-png.html) — Extract PDF pages as images
- [WebP to JPG](https://purpledoubled.github.io/file-converter/webp-to-jpg.html) — Fix incompatible web images

## ✨ Features

- 🔐 **100% client-side** — zero server processing
- 📁 **Drag & drop** — or click to browse
- 📦 **Batch convert** — multiple files → ZIP download
- 📱 **Mobile-friendly** — works on any device
- ⚡ **Instant** — no waiting for server round-trips
- 🆓 **Free** — 5 conversions/day free, unlimited for $2.99 one-time

## 🛠 Tech

Single HTML file. No build tools, no frameworks, no dependencies to install.

- [pdf.js](https://mozilla.github.io/pdf.js/) (Mozilla) — PDF rendering
- [jsPDF](https://github.com/parallax/jsPDF) — PDF creation
- [libheif-js](https://github.com/nicofisch/libheif-js) — HEIC decoding (WASM)
- [JSZip](https://stuk.github.io/jszip/) — ZIP packaging
- Canvas API — Image format conversion

## 🚀 Self-Host

It's a single HTML file. Download it and open in any browser:

```bash
git clone https://github.com/PurpleDoubleD/file-converter.git
cd file-converter
open index.html
```

## License

MIT
