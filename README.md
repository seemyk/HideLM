# HideLM

**HIDE FEATURED NOTEBOOKS**

Minimal Chrome/Chromium extension that hides NotebookLM’s **Featured Notebooks** UI:

- The **Featured Notebooks section** on the dashboard
- The **“Featured notebooks” tab** in the top toggle bar

Works on: `https://notebooklm.google.com/*`

## Install (Developer mode)

1. Open Chrome (or another Chromium browser).
2. Go to `chrome://extensions`.
3. Enable **Developer mode** (top-right).
4. Click **Load unpacked**.
5. Select this folder (`no-featured-notebooklm/`).
6. Open NotebookLM and refresh the page.

## Update after changes

1. Go to `chrome://extensions`.
2. Click **Reload** on “HideLM”.
3. Hard refresh NotebookLM (`Cmd+Shift+R` on macOS / `Ctrl+Shift+R` on Windows/Linux).

## What it changes

This extension only injects CSS (`styles.css`) and does not run any JavaScript.

Current selectors:

- Hides the Featured Notebooks dashboard section via `.featured-projects-container`
- Hides the top “Featured notebooks” toggle via `mat-button-toggle:has(.editors-picks-toggle-label)`

## Troubleshooting

- **The tab/section is still visible**
  - NotebookLM likely changed its DOM/classes.
  - Inspect the visible UI in DevTools and update the selector(s) in `styles.css`.

- **Nothing changes at all**
  - Confirm the extension is enabled.
  - Confirm you loaded the correct folder (the one containing `manifest.json`).
  - Confirm you’re on `https://notebooklm.google.com/…`

## Packaging / sharing

### Share on GitHub

This repo is already suitable for sharing as source.

### Create a zip for friends (manual install)

1. Zip the folder contents (must include `manifest.json` at the root of the zip).
2. The recipient can unzip and use **Load unpacked** as described above.

### Chrome Web Store notes

If you publish to the Chrome Web Store, upload the same artwork as `Assets/store_icon.png`
for the 128×128 listing icon, and include a clear privacy statement (see `PRIVACY.md`).
Promotional images live in `Assets/` (`small_tile.png`, screenshots) — upload those in the
developer dashboard only; they do not need to be inside the `.zip` you submit (the package
only needs `manifest.json`, `styles.css`, and `Assets/store_icon.png`).

