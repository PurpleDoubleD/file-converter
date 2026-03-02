---
title: I Built a Privacy-First File Converter After the FBI Warned About Malicious Ones
published: false
description: A 100% client-side file converter that never uploads your files. Built with vanilla JS, pdf.js, and Canvas API.
tags: webdev, javascript, privacy, opensource
cover_image:
---

Last March, the FBI [issued a warning](https://www.ic3.gov/PSA/2025/PSA250313) about free online file converters being used to distribute malware and steal personal data.

That got me thinking: **why do file converters need a server at all?**

Modern browsers can handle image manipulation, PDF rendering, and format conversion natively. So I built a converter that does everything client-side. Your files literally never leave your browser tab.

## What It Does

- **JPG ↔ PNG ↔ WebP** — standard image conversions
- **PDF → PNG/JPG** — extract pages as images
- **Images → PDF** — combine images into a PDF
- **HEIC → JPG** — convert iPhone photos
- **SVG → PNG/JPG** — rasterize vector graphics

All processing happens in your browser using JavaScript.

## The Tech (It's Surprisingly Simple)

The entire app is a **single HTML file**. No build step, no framework, no server.

### Image Conversions: Canvas API

```javascript
// Load image, draw to canvas, export as different format
const canvas = document.createElement('canvas');
const ctx = canvas.getContext('2d');
canvas.width = img.width;
canvas.height = img.height;
ctx.drawImage(img, 0, 0);

// Change the MIME type = change the format
const blob = await new Promise(r => 
  canvas.toBlob(r, 'image/webp', 0.92)
);
```

That's it. The browser does the heavy lifting.

### PDF Rendering: pdf.js

Mozilla's [pdf.js](https://mozilla.github.io/pdf.js/) renders PDF pages to a canvas element. From there, it's the same `toBlob()` trick to export as PNG or JPG.

### PDF Creation: jsPDF

[jsPDF](https://github.com/parallax/jsPDF) creates PDFs from images. Load image → detect dimensions → create PDF with matching page size → add image.

### HEIC Decoding: libheif-js

Apple's HEIC format needs a WASM decoder. [libheif-js](https://github.com/nicofisch/libheif-js) handles this — decode HEIC → get pixel data → draw to canvas → export as JPG.

### Batch Downloads: JSZip

Multiple files? [JSZip](https://stuk.github.io/jszip/) packages them into a ZIP that downloads as a single file.

## Why No Server?

1. **Privacy** — files never leave the device
2. **Speed** — no upload/download latency
3. **Cost** — zero server costs, hosted free on GitHub Pages
4. **Reliability** — works offline once loaded
5. **Trust** — open source, inspect the code yourself

## Try It

🔗 **[purpledoubled.github.io/file-converter](https://purpledoubled.github.io/file-converter/)**

📦 **[Source on GitHub](https://github.com/PurpleDoubleD/file-converter)** — MIT licensed

Dedicated guides:
- [HEIC to JPG](https://purpledoubled.github.io/file-converter/heic-to-jpg.html)
- [PDF to PNG](https://purpledoubled.github.io/file-converter/pdf-to-png.html)
- [WebP to JPG](https://purpledoubled.github.io/file-converter/webp-to-jpg.html)

---

Would love feedback on the UX. What formats would you add next?
