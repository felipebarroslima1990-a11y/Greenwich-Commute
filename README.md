# Greenwich Home (v10)

A home-screen web app for choosing between Cannon Street and the DLR when leaving the office.

## Decision rule
- Assumes a 15-minute walk from the office to Cannon Street platforms.
- Requests Cannon Street departures with `calling_at=GNW`, which means the train calls at Greenwich later on this same departure.
- Independently confirms that Greenwich (GNW) appears in that departure's own forward `calling_points`. No Deptford → Greenwich → Maze Hill sequence is required.
- Uses an actual or forecast departure time when available. For `no_information`, it uses the scheduled time and labels it as timetable-based. It does not use scheduled time for `delayed_no_estimate` or cancelled services.
- Requires departure at or after the estimated arrival and no later than 10 minutes after arrival.
- Displays the destination and forward calling points for the selected service.
- Includes expandable diagnostics: API rows returned, forward Greenwich calls, usable departure times, qualifying trains, rejection counts, and examples.
- If no suitable train can be verified, recommends the DLR.

## Deploy
Upload the contents of this folder to the existing Netlify site (publish directory `.`). The service-worker cache has been bumped to v10.

Personal, non-commercial use. Live data from traini.ac.
