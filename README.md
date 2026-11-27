# Inkleaf Manga Reader

A fast, private manga reader that runs entirely in your browser. Open a **PDF** or a **folder of page images** and read in three modes: page flip, vertical scroll, or an auto-panning cinema view.

No build step, no backend, no account. Just static files.

## Features

- **Flip mode** – 3D page turns, with two-page spreads on wide screens
- **Scroll mode** – one continuous vertical strip, webtoon style
- **Cinema mode** – pans down each page and fades into the next, with play/pause and 0.5x to 2x speed
- **Right-to-left or left-to-right** reading direction
- **Page tones** – Paper, Night and Sepia
- **Zoom and pan** – double-tap or pinch to zoom, drag to move
- **Page grid** for jumping to any page, plus a scrubber bar
- **Resume reading** – your last page is remembered per file
- **Responsive** – works on phones, tablets and desktops, with light and dark themes
- **Private** – files never leave your device

## Supported input

- PDF files (rendered with pdf.js)
- Image files or folders of images (JPG, PNG, WebP, etc.), sorted in natural order (`page2` before `page10`)

## Getting started

### Option 1: Open directly
Download or clone the repo and double-click `index.html`.

### Option 2: Local server
```bash
python3 -m http.server 8000
```
Then open http://localhost:8000

### Option 3: Host it
Upload the whole folder to any static host.

**GitHub Pages:**
1. Push this repo to GitHub.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, then save.
4. Your reader will be live at `https://<your-username>.github.io/<repo-name>/`.

Netlify and Vercel work the same way: drag in the folder, no configuration needed.

## Controls

| Action | Touch | Keyboard |
|---|---|---|
| Next / previous page | Tap left or right edge, or swipe | Arrow keys |
| Zoom | Double-tap or pinch | – |
| Pan (when zoomed) | Drag | – |
| Show / hide bars | Tap the centre | – |
| Switch mode (Flip / Scroll / Cinema) | Top bar | `1` / `2` / `3` |
| Reading direction | Top bar | `D` |
| Page tone | Top bar | `T` |
| Page grid | Bottom bar | `G` |
| Fullscreen | Top bar | `F` |
| First / last page | – | `Home` / `End` |

## Project structure

```
inkleaf/
├── index.html          # the whole app (HTML, CSS and JS)
└── lib/
    ├── pdf.min.js          # pdf.js 3.11.174
    └── pdf.worker.min.js   # pdf.js worker
```

PDF support is bundled in `lib/`, so PDFs open without an internet connection. The UI fonts (Dela Gothic One and Zen Kaku Gothic New) load from Google Fonts; offline, the page falls back to system fonts.

## Privacy

Everything happens locally in your browser. Your files are never uploaded. Only your reading preferences (mode, direction, tone, speed) and last-read page are saved, in your browser's `localStorage`.

## Credits

- [pdf.js](https://mozilla.github.io/pdf.js/) by Mozilla (Apache-2.0)
- Fonts: [Dela Gothic One](https://fonts.google.com/specimen/Dela+Gothic+One) and [Zen Kaku Gothic New](https://fonts.google.com/specimen/Zen+Kaku+Gothic+New)

## License

Add a license of your choice (for example MIT) as a `LICENSE` file before publishing.
