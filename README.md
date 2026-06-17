# Formula Feed Calculator (web app)

A self-contained, installable web app version of the Formula Feed Calculator.
Everything runs in the browser — no backend, no network calls. Settings are
stored only on the device (`localStorage`).

## Files
- `index.html` — the calculator (all CSS + JS inline)
- `manifest.webmanifest` — PWA metadata (name, icons, colours)
- `sw.js` — service worker (offline caching)
- `icon.svg`, `icon-192.png`, `icon-512.png`, `icon-maskable-512.png`, `apple-touch-icon.png` — app icons

## Deploy to GitHub Pages
1. Create a new repository on github.com (e.g. `feed-calculator`).
2. Upload the contents of this folder to the repo (drag-and-drop in the web UI works).
3. Repo **Settings → Pages** → *Build and deployment* → Source: **Deploy from a branch**,
   Branch: **main** / **/(root)** → Save.
4. The live URL appears in ~1 minute, e.g. `https://<username>.github.io/feed-calculator/`.

## Install on a phone
- **iOS (Safari):** open the URL → Share → **Add to Home Screen**.
- **Android (Chrome):** open the URL → menu (⋮) → **Install app** / **Add to Home screen**.

## Updating later
After changing `index.html`, bump `CACHE_VERSION` in `sw.js` (e.g. `feedcalc-v2`)
so installed users get the new version, then re-upload.

## Test locally
Service workers need an `http://` origin (not `file://`). Run `_serve.ps1` in
PowerShell, then open `http://localhost:8123/`.
