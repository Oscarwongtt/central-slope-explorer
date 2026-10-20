# Central Slope Explorer — real walking routes

An interactive Form 3 Chapter 10 mathematics investigation for Central and Mid-Levels, Hong Kong.

## What's new
- Click **A** and **B** on the Google map, or type two locations.
- Request up to **three routes actually returned by Google Maps** in WALKING mode (fewer may be available).
- Sample approximate terrain elevation along the *curved pedestrian route*, not the straight line between endpoints.
- Divide routes into roughly 50 m / 100 m / 200 m **horizontal path-distance sections**.
- Calculate signed section gradient (%) and angle (degrees) before revealing results.
- Compare available routes using walking distance and estimated steepest uphill section.
- Export an investigation report. A separate contour-reference map is included.

## Required Google Maps configuration
This is a static GitHub Pages website. Google routing **cannot work until you configure a Google Maps Platform browser API key**:

1. In [Google Cloud Console](https://console.cloud.google.com/), create/select a project and enable billing.
2. Enable **Maps JavaScript API**, **Routes API**, and **Elevation API**.
3. Create a browser API key restricted by HTTP referrer to `https://oscarwongtt.github.io/*`, and by API to the enabled Maps APIs. Configure quotas and budget alerts.
4. Edit [google-config.js](google-config.js) in GitHub and replace the empty value of `window.CENTRAL_GOOGLE_MAPS_KEY` with your **restricted browser key**.
5. If Pages is enabled on branch `main` from `/(root)`, test [the live site](https://oscarwongtt.github.io/central-slope-explorer/).

You can also test privately: open the site, click **Google Maps setup**, and enter the browser key for that session. **Do not put an unrestricted/server-secret key in this public repository.** Google Maps may incur charges. Some school/Hong Kong networks may block Google services.

## Important mathematics / reliability warnings
- The returned paths come from Google's pedestrian routing network, but may not include every walkway; verify local pedestrian safety and accessibility.
- Google elevation values approximate **terrain**, not the road or footbridge walking surface. Contour maps alone do not provide authoritative road gradients.
- Section gradients depend on sample spacing, section length, DEM resolution, and the route polyline. Particularly short sections can produce unreliable steepness estimates.
- The route-choice threshold is a **fictional classroom criterion**, not an official pedestrian safety or accessibility standard.
- Google may return fewer than three walking alternatives; none are invented.
- The non-Google topographic reference tab does **not** display Google routing geometry.

## Data storage
The website stores student predictions, completed section calculations and final recommendation locally. It does not intentionally persist Google's route-geometry or elevation responses in localStorage.

[Google Maps Routes documentation](https://developers.google.com/maps/documentation/javascript/routes/get-alternative-routes) · [Elevation service](https://developers.google.com/maps/documentation/javascript/elevation) · [Security recommendations](https://developers.google.com/maps/api-security-best-practices)
