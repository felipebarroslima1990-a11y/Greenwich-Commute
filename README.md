# Greenwich Home (v6)

A small home-screen web app for choosing between Cannon Street and the DLR when leaving the office.

## Decision rule
- Assumes a 15-minute walk from the office to Cannon Street platforms.
- Recommends Cannon Street only when a direct passenger journey from station code CST to station code GNW is explicitly returned by the traini.ac journey API, and its predicted departure is after estimated arrival but less than 10 minutes later.
- Connecting journeys, other destinations, missing route information, API errors, and unverified results are rejected; the app recommends the DLR instead.
- Uses live data and refreshes when opened or when the refresh button is tapped.
- Separately reads the Cannon Street departure board and matches the exact train by train ID to display its advertised destination, platform/headcode, and ordered calling points. The API does not document a separate verbatim passenger-facing “via” string, so the app labels the ordered stops “Via / calling points”; this makes the Greenwich stop visible without pretending to reproduce the exact board wording. The journey endpoint remains the source for checking the Greenwich stop.

## Deploy
Upload the contents of the `greenwich-commute-app` folder to the existing Netlify site (publish directory `.`). This is v4 and uses a new service-worker cache name to avoid retaining the old app cache.

Personal, non-commercial use. Live data from traini.ac.
