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

## V1.6 save/load cleanup
Saved entries are snapshots. Save as new creates another saved entry. Load brings a saved entry back into the form. New blank clears the form for a new calculation. Saved data stays on-device in localStorage.

## V1.7 auto-save
Current working door/unit auto-saves to localStorage about 2 seconds after the last change. Saved entries remain separate named snapshots. All data stays on-device.

## V1.8 named saved options
Saved entries are stored by Entry name / job label. Saving a new name creates a new option. Saving a name that already exists updates the existing option instead of creating duplicate versions. Current work still auto-saves separately.

## V1.9 cleanup
Removed the Phone scale tab because the app layout already scales responsively. Cut list wording now says selected slab before cut and finished door size to avoid confusing the original slab size with the final cut door size.

## V1.10 button cleanup
Removed the development test button and manual Calculate button. Results update automatically as fields change. Main actions are Copy cut list, Save/update, and New blank.

## V1.11 recommended RO
Added recommended rough opening display for fixed-width door setups and non-transom height cases. Warnings now use tolerances so small acceptable differences do not over-alert. Added a temporary cut-down notice when the selected slab must be cut shorter.

## V1.12 no-cut RO suggestion
When a non-transom door needs to be cut down, the warning, popup, and cut list now show the rough opening height that would be needed to avoid cutting the selected slab.

## V1.13 blocking width validation
Added blocking validation for door-only widths where the selected slab cannot fit the entered rough opening. Fiberglass doors cannot be cut narrower. Wood doors require custom width/selecting a smaller slab when the RO is too narrow. Blocking errors are shown before normal outputs and included in the cut list as DO NOT USE.
