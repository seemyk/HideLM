# HideLM

**HIDE FEATURED NOTEBOOKS**

Minimal browser extension for **Chrome/Chromium** and **Firefox** that hides NotebookLM’s **Featured Notebooks** UI:

- The **Featured Notebooks section** on the dashboard
- The **“Featured notebooks” tab** in the top toggle bar

Works on: `https://notebooklm.google.com/*`

**Firefox:** version **121 or newer** is required for the top-tab hide rule (CSS `:has()`). Older Firefox versions may still hide the dashboard section only.

## Install from the Chrome Web Store

https://chromewebstore.google.com/detail/hidelm/kmkpdkgdplhgngfhnopohaabnmignije

## Install (Developer mode)

### Chrome / Chromium

1. Open Chrome (or another Chromium browser).
2. Go to `chrome://extensions`.
3. Enable **Developer mode** (top-right).
4. Click **Load unpacked**.
5. Select this folder (the one containing `manifest.json`).
6. Open NotebookLM and refresh the page.

### Firefox

1. Open Firefox **121 or newer**.
2. Go to `about:debugging`.
3. Click **This Firefox** (left sidebar).
4. Click **Load Temporary Add-on…**.
5. Select `manifest.json` in this folder.
6. Open NotebookLM and refresh the page.

## Update after changes

### Chrome / Chromium

1. Go to `chrome://extensions`.
2. Click **Reload** on “HideLM”.
3. Hard refresh NotebookLM (`Cmd+Shift+R` on macOS / `Ctrl+Shift+R` on Windows/Linux).

### Firefox

1. Go to `about:debugging` → **This Firefox**.
2. Click **Reload** on HideLM (or remove and load the add-on again).
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
  - On Firefox, confirm you’re on version 121+ if the top tab is still visible.

## Support

If this extension saved you from daily dashboard clutter, consider offering me a coffee!

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/seemyk1)

## Packaging / sharing

### Create a zip for friends (manual install)

1. Zip the folder contents (must include `manifest.json` at the root of the zip).
2. The recipient can unzip and install using **Load unpacked** (Chrome) or **Load Temporary Add-on…** (Firefox) as described above.

### Chrome Web Store

HideLM is published on the [Chrome Web Store](https://chromewebstore.google.com/detail/hidelm/kmkpdkgdplhgngfhnopohaabnmignije). The upload package needs `manifest.json`, `styles.css`, and icon PNGs under `Assets/`. See [PRIVACY.md](PRIVACY.md) for the privacy statement.

### Firefox / AMO notes

The same root folder works for Firefox. Privacy policy: [PRIVACY.md](PRIVACY.md) (hosted on GitHub at `https://github.com/seemyk/HideLM/blob/main/PRIVACY.md`).

To publish on [addons.mozilla.org](https://addons.mozilla.org):

1. From the folder containing `manifest.json`, zip only the extension files (manifest, `styles.css`, `Assets/icon-16.png`, `Assets/icon-48.png`, `Assets/icon-128.png`) — files at the **root** of the zip, not inside a subfolder; exclude `.DS_Store` and `__MACOSX`.
2. Sign the add-on ([web-ext sign](https://extensionworkshop.com/documentation/develop/getting-started-with-web-ext/) with AMO API credentials, or upload source in the developer hub).
3. Submit the signed `.xpi` (or source zip), listing copy, screenshots, privacy policy URL, and support email **seemyk1+info@gmail.com**.

`browser_specific_settings.gecko.id` is a fixed UUID in `manifest.json` — do not change it after the first public AMO release.
