# 🔒 Private File Converter

**Convert files directly in your browser. Nothing gets uploaded. Ever.**

🌐 **[Use it now →](https://purplefbihaze-cpu.github.io/file-converter/)**

## Why?

The FBI [recently warned](https://www.ic3.gov/PSA/2025/PSA250313) about online file converters stealing personal data. This converter runs **100% in your browser** — your files never leave your device.

## Supported Conversions

| From | To |
|------|-----|
| JPG, PNG, WebP | PDF |
| PDF | PNG, JPG |
| HEIC (iPhone) | JPG |
| WebP | PNG, JPG |
| SVG | PNG |

## Features

- 🔐 **100% client-side** — zero server processing
- 📁 **Drag & drop** — or click to browse
- 📦 **Batch convert** — multiple files → ZIP download
- 📱 **Mobile-friendly** — works on any device
- ⚡ **Instant** — no waiting for server round-trips
- 🆓 **Free** — no accounts, no limits, no tracking

## Tech

Single HTML file. No build tools, no frameworks. Uses:
- [pdf.js](https://mozilla.github.io/pdf.js/) (Mozilla) — PDF rendering
- [jsPDF](https://github.com/parallax/jsPDF) — PDF creation
- [libheif-js](https://github.com/nicofisch/libheif-js) — HEIC decoding (WASM)
- [JSZip](https://stuk.github.io/jszip/) — ZIP packaging

## License

MIT
