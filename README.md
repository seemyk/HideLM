# HideLM

**HIDE FEATURED NOTEBOOKS**

Minimal Chrome/Chromium extension that hides NotebookLM’s **Featured Notebooks** UI:

- The **Featured Notebooks section** on the dashboard
- The **“Featured notebooks” tab** in the top toggle bar

Works on: `https://notebooklm.google.com/*`

## Install on Chrome Web Store
https://chromewebstore.google.com/detail/hidelm/kmkpdkgdplhgngfhnopohaabnmignije

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



