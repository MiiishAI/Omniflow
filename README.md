# Omniflow

Omniflow is a static HTML/PWA productivity dashboard. It is designed to run in a browser and can appear "dead" if opened directly from the filesystem.

## How to run it correctly

Do not open `index.html` directly with `file:///...` in the browser.

Instead, serve the project from a local web server:

### Option 1: with Python

From the project root:

```bash
python3 -m http.server 8000
```

Then open:

```text
http://localhost:8000/
```

### Option 2: using the helper script included in this repo

```bash
python3 start-local.py
```

Then open:

```text
http://localhost:8000/
```

## Why this matters

This app uses a service worker (`sw.js`) and browser-side storage (`localStorage`). Those features are only reliable when the page is served over `http://localhost` or `https://`.

If you open the HTML file directly from disk (`file://`), some UI features may fail to register or appear unresponsive.

## Troubleshooting

- Open the browser dev tools with F12
- Check the Console tab for JavaScript errors
- Make sure the page is loaded from `http://localhost:8000/`
- If needed, hard-refresh the page after starting the server

## Notes

This repository is a front-end prototype. It stores tasks/settings in the browser and does not require a backend server to function locally.
