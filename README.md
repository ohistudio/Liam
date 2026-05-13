# Liam Mason · ohi Studio — portfolio site

A single-file static site for GitHub Pages.

## Local preview

From this folder:

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000 in Chrome or Safari.

## What goes where

```
ohi-website/
├── index.html                  ← the whole site (HTML + CSS + JS)
├── README.md                   ← this file
├── business-card-PRINT.html    ← print-to-PDF source for the AWE business card
└── media/
    ├── in-field-spectacles.jpg ← the candid Spectacles testing shot
    ├── portrait.jpg            ← (you add) — your About-section solo portrait
    ├── reel.mp4                ← (you add) — top-of-page sizzle reel (loops, muted, no audio needed)
    ├── reel-poster.jpg         ← (you add) — fallback poster image for reel.mp4
    ├── pool.mp4 + pool-poster.jpg          ← Pool Assist clip
    ├── darts.mp4 + darts-poster.jpg        ← Darts Mate clip
    ├── iyo-vr.mp4 + iyo-vr-poster.jpg      ← Iyo (VR) clip
    ├── iyo-roll.mp4 + iyo-roll-poster.jpg  ← Iyo Roll clip
    ├── whereabouts.mp4 + whereabouts-poster.jpg
    ├── asym.mp4 + asym-poster.jpg
    ├── specdeck.mp4 + specdeck-poster.jpg
    ├── blobble.mp4 + blobble-poster.jpg
    ├── flow.mp4 + flow-poster.jpg
    ├── bitfarm.mp4 + bitfarm-poster.jpg
    ├── dance.mp4 + dance-poster.jpg
    └── fishing.mp4 + fishing-poster.jpg
```

## Video specs

- Format: `.mp4` (H.264 codec)
- Length: 8–15 seconds, looping (no audio needed — they autoplay muted)
- Dimensions: 1280×720 or 1920×1080 (16:9)
- Target file size: 1–3 MB each (GitHub Pages caps total repo at 1GB; aim under 100MB total)
- Compression tip (Mac): `ffmpeg -i input.mov -c:v libx264 -crf 28 -preset slow -an -vf scale=1280:-2 output.mp4`

## Deploying to GitHub Pages

1. Create a repo on GitHub named `liammason.github.io` (using your username)
2. Drop everything in this folder into the repo's root
3. Push — GitHub Pages serves it automatically from `main` branch
4. Site goes live at `https://liammason.github.io` within a minute
5. (Optional) Point `liam.ohi.studio` to it: add a CNAME file containing the line `liam.ohi.studio`, then in your DNS panel set a CNAME record from `liam` → `liammason.github.io`

## Editing copy or projects

The site is one HTML file. Search for the project name (e.g. `Pool Assist`) and you'll find both the English and Chinese strings — the bilingual toggle is JS-powered, both texts live inline.

## Business card

Open `business-card-PRINT.html` in Chrome to generate the print PDF — instructions are in the page itself.
