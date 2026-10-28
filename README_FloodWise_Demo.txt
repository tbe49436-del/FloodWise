FloodWise — Interactive Web Demo
================================

Files
- FloodWise_Demo.html: single-file responsive HTML/CSS/JavaScript prototype.

What works in the mockup
- Dashboard with sample alert levels and area cards.
- Map view with Google Maps JavaScript API if the key/API/billing/referrer setup permits it; a demo map fallback appears if the map cannot load.
- Vehicle selector and route A/B selection. Lines, flood depth, locations, and routes are simulated, not live routing.
- Emergency request form, GPS permission action, request status tracking, and response dashboard workflow.
- SME goods inventory, automatic priority score, move checklist, time readiness estimate, adding/removing items, and CSV export.
- Community report creation and demo verification.
- Alert settings and local browser storage so entries remain after refreshing the same browser.

Important limitations
- The app is a mockup. Flood risk, water depth, locations, reports, route geometry, and help requests are sample data; no emergency dispatch service is connected.
- A Google Maps API key in browser code is visible to anyone using the page. Restrict the key by HTTP referrer and restrict it to the Google Maps JavaScript API in Google Cloud Console. Enable the API and billing for the same project.
- For local testing with an HTTP-referrer-restricted key, serve the file over localhost rather than opening file:// directly:
    1. Open a terminal in the folder containing FloodWise_Demo.html
    2. Run: python -m http.server 8000
    3. Open: http://localhost:8000/FloodWise_Demo.html
    4. In Google Cloud Console, allow the local referrer, e.g. http://localhost:8000/* (and restrict to your deployed domain later).
- If Google Maps does not load, the mock map remains available. Check the browser console for billing, API activation, or referrer restrictions.
- The GPS button requires the browser's location permission and a secure context (localhost is treated as secure by modern browsers).
- Emergency numbers displayed are reference information from the project brief; verify them with official sources before any real-world deployment.

Next steps for production use
- Replace mock data with verified API feeds and display source timestamps / staleness warnings.
- Implement authentication, server-side authorization, a secure database, audit logging, privacy policy, consent, retention/deletion rules, and backups.
- Connect emergency requests only through an agreed and staffed operational workflow.
- Do not label a route “safe” unless verified against current road and flood conditions.
