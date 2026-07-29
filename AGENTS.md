# MedsADay

Single-file PWA medication tracker. No build step, no framework, no dependencies.

## Architecture

Everything lives in `index.html` (HTML + CSS + JS). `sw.js` is the service worker. That's it.

- All state is in `localStorage` — no server, no database
- Dark theme is default (`:root`), light theme via `[data-theme="light"]` on `<html>`
- Accent colors have `-rgb` CSS variable variants for use in `rgba()`
- Medication pill colors: `--c-blue`, `--c-purple`, etc. — each has a `-rgb` counterpart per theme
- JS `COLORS` object switches between `DARK_COLORS` / `LIGHT_COLORS` based on theme
- Mock Dropbox activates when app key is `"mock"` (case-insensitive)

## Commands

No build or test commands. Open `index.html` in a browser, or deploy to any static host.

PowerShell on Windows — use `;` not `&&` to chain commands.

## Committing

Each bug fix or feature change gets its own commit. Never batch unrelated changes.

## Gotchas

- Version string: update both the `.version` span in the titlebar HTML and the top entry in `changelog.txt`
- `sw.js` `ASSETS` array must list every cached file — update it when adding new static assets
- `manifest.webmanifest` icons array must match the actual icon files
- Grid layout on `.window` uses `grid-template-rows` — titlebar is `auto`, body is `1fr`
- All CSS is scoped inside `<style>` in `index.html` — there are no external stylesheets
