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

## V1.14 single door width rule
Confirmed single-door header/rough-opening width logic. Stock single doors use industry-standard RO width based on nominal door width + 2 inches, so a 3'0" fiberglass or wood door both show 38" RO width. Single door actual cut header is the recommended RO width minus 2 inches. Removed the single-door header/transom width confirmation warning.

## V1.15 actual slab transom width
Separated recommended rough opening width from actual header/transom width. Stock single-door recommended RO still uses nominal width + 2 inches, but actual cut header and T/D transom width are based on actual slab width. Double-door transom sizing continues to use actual slab widths, astragal, and gaps, so fiberglass and wood door pairs produce different header/transom widths and transom heights.

## V1.16 shop-accurate RO correction
Removed the nominal-width same-RO shortcut. Single-door recommended rough opening width now uses actual slab size consistently: actual cut header = actual slab width + 1/4 inch, recommended RO width = actual cut header + 2 inches, and T/D transom glass width = actual cut header - 1/8 inch. This prevents conflicts between fiberglass and wood slab sizing.

## V1.17 smaller door sizes
Added 2'10", 2'8", and 2'6" x 6'8" door size options. D and T/D allow 2'6", 2'8", and 2'10" widths. DD and T/DD include 2'6" x 6'8". Sidelight configurations block widths smaller than 3'0" to avoid bad front-entry glass unit suggestions.
