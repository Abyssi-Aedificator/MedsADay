# MedsADay — Medication Tracker

Privacy-first medication tracker. All data stays on your device — no accounts, no servers, no tracking.

## Features

- **Schedule & track doses** — add medications with custom times, doses, and date ranges
- **Daily adherence** — see today's progress, streak, next dose, and refill alerts at a glance
- **History & reports** — full intake log with adherence trends, per-medication stats, and breakdown by time of day
- **Local notifications** — browser-based reminders when a dose is due (installable PWA)
- **Offline-ready** — service worker caches everything; works without internet
- **Backup & restore** — export your data as a JSON file
- **Dropbox sync (optional)** — bring your own Dropbox App key for cross-device sync via PKCE OAuth2 — data goes directly between your browser and Dropbox, never through a server

## Usage

1. Open `index.html` in any modern browser (or deploy to any static host)
2. Add your medications via the **＋ Add medication** button
3. Tap ✓ to mark a dose taken, ✕ to skip
4. Install as a PWA via your browser's menu for offline use and local reminders

## Tech

Vanilla JS single-page app with `localStorage` persistence. No frameworks, no build step, no dependencies. PWA features via service worker and web app manifest.

## Deploy

Any static file server works. For GitHub Pages, push the repo and enable Pages from the root of the `main` branch.

```
medsaday/
├── index.html            # App shell (HTML + CSS + all JS)
├── sw.js                 # Service worker (offline cache)
├── manifest.webmanifest  # PWA manifest
├── icon-192.png
├── icon-512.png
├── icon-maskable.png
└── README.md
```
