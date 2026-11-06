# Greenwich Home — first prototype

A tiny installable web app that opens straight to a DLR vs Cannon Street recommendation.

## Current assumptions
- Office → Cannon Street platforms: **15 minutes**
- Maximum acceptable wait after reaching Cannon Street: **10 minutes**
- Cannon Street station code: `CST`
- Greenwich station code: `GNW`
- Live data: `https://api.traini.ac/v1/departures/CST?calling_at=GNW&limit=100`

## Deploy
Upload all five files in this folder to the root of a static HTTPS site: `index.html`, `manifest.webmanifest`, `sw.js`, `icon.svg`, and `README.md` (README is optional). Then open the HTTPS site in Safari on iPhone → Share → Add to Home Screen.

## Data source note
This prototype uses traini.ac's browser-accessible REST API. It is a third-party service, so live-data availability and its terms should be checked before relying on it. The app falls back to the DLR if the service cannot be reached or no qualifying train is found.
