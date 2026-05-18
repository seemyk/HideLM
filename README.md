# HideLM

**HIDE FEATURED NOTEBOOKS**

Minimal Chrome/Chromium extension that hides NotebookLM’s **Featured Notebooks** UI:

- The **Featured Notebooks section** on the dashboard
- The **“Featured notebooks” tab** in the top toggle bar

Works on: `https://notebooklm.google.com/*`

## Install from the Chrome Web Store
https://chromewebstore.google.com/detail/hidelm/kmkpdkgdplhgngfhnopohaabnmignije

## What it changes

This extension only injects CSS (`styles.css`) and does not run any JavaScript.

Current selectors:

- Hides the Featured Notebooks dashboard section via `.featured-projects-container`
- Hides the top “Featured notebooks” toggle via `mat-button-toggle:has(.editors-picks-toggle-label)`

## Support

If this extension saved you from daily dashboard clutter, consider offering me a coffee!

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/seemyk1)



