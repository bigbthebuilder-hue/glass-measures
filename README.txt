# Glass Measures V1.2

Install-ready PWA package for desktop browsers, with a phone-scale result view inside the app.

## Files
- index.html
- manifest.webmanifest
- service-worker.js
- icons/icon-192.png
- icons/icon-512.png

## Desktop install
Best method:
1. Put this folder in a GitHub repo.
2. Deploy it with Vercel.
3. Open the Vercel app link in Chrome or Edge.
4. Click the install icon in the address bar, or use the browser menu > Install Glass Measures.

Local test method:
1. Open a terminal in this folder.
2. Run: python -m http.server 8080
3. Open: http://localhost:8080
4. Install from Chrome or Edge.

Directly double-clicking index.html will open the app, but desktop install usually will not appear because service workers need http/https.

## Saved entries
Saved entries use browser localStorage only. They stay on the device/browser and are not shared.

## V1.5 height logic update
For non-transom units, final door height is capped at the actual selected slab height. If the rough opening is taller than the selected slab/unit, jamb legs are calculated from the final door height and sidelights remain final door height + 1/8 inch.
