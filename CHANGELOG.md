# Changelog

What changed in each TacTrace release, newest first. Downloads are on the
[Releases](https://github.com/orbat-mapper/tactrace-public/releases) page.

## 1.9.1 - 2026-09-26

### Fixes

- Curved attack arrows now join the arrowhead cleanly. Previously the shaft could meet the head with a visible kink or gap.

### Under the hood

- control-measures updated to 0.29.1.

## 1.9.0 - 2026-09-26

### New

- **Variable-width arrows**: turn on **Width grips** in the **Details Panel** or the mobile toolbar to drag an arrow's width at each vertex. Alt+click a grip to reset it, or use **Reset arrow widths** to reset them all.

### Improvements

- Measures that support different smoothing styles now offer **Rounded** and **Curve** toggles in place of the single **Smooth** toggle.
- **About TacTrace** now links to the release notes, a page for reporting bugs and requesting features, and a contact email.

### Under the hood

- Dependencies updated, including control-measures 0.29.0 and tactical-draw 0.11.0.

## 1.8.0 - 2026-09-26

### New

- **Roadblocks, craters and blown bridges**: four new protection measures: Planned, Explosives (safe), Explosives (armed but passable), and Roadblock complete. Draw them with three points; the third sets the width.
- **Keep a copy**: exploring an example no longer saves a copy to **Maps on this device** on your first change. Your edits stay in the example until you choose **Keep a copy** (in the menu pill, the File menu, or the command palette), save a Map File, or rename the Map. Leaving an example with unkept edits asks first; tick **Do not show this warning again** to stop it, and turn it back on with **Warn before discarding example changes** in Preferences.

### Improvements

- The start page and **About TacTrace** show which version of TacTrace you are running, with a link to its release notes.
- Every Map now opens on the **Layers** tab of the sidebar.
- Focus and selection highlights in the Maps list, the Examples gallery, the editing toolbar and the PMTiles archives dialog are no longer cut off at the edges.

### Fixes

- A Map whose saved view had become invalid now opens at the default view. Previously it could be listed as unavailable or fail to show the map.

### Under the hood

- Dependencies updated, including control-measures 0.28.0, tactical-draw 0.10.2, and maplibre-gl 6.11.2.

## 1.7.1 - 2026-09-25

Changes since 1.6.0.

### New

- **Paste at view center** (Alt+Shift+V, also in the Edit menu): pastes copied items in the middle of the current view. Turn on **Always paste at view center** to make every paste do this.
- **Paste here**: a new item in the map's right-click menu that pastes copied items centered on the point you clicked. Pasted items keep their size and orientation on the ground.
- **Orbit demo mode**: a presentation tool (hotkey **O**) that slowly circles the camera around a point on the map. Click the map to choose a new center.
- **Presentation tools menu**: the laser pointer and orbit demo share a split button in the desktop toolbar. The main button re-arms whichever of the two you used last.
- **Terrain and hillshade control**: a new map control on desktop turns terrain and hillshade on and off together.
- **Pin settings**: adjust pin height, width, color and halo, and symbol size and halo, for the experimental pin rendering modes. Symbol rendering options are also in the map's right-click menu.

### Improvements

- Settings menus are reorganized: snapping and measurement options are grouped together, and terrain and symbol rendering have their own menus.
- Click a map card in the map library to open that map.
- The start page is now in the main menu.
- When the Details Panel is docked on the right, the map controls line up in a row so they don't run into the panel.
- The map compass has a dark-mode style.
- Terrain menus use a mountain icon.
- Hover highlights respond faster when terrain is on.
- Box selection picks pins where they are drawn, including raised pins.
- Self-hosted installations can list the terrain source's tile URLs directly in the configuration file instead of a TileJSON URL.

### Fixes

- Pasting, and dragging Layers Panel rows or Favorite measures onto the map, no longer distorts graphics when the map is tilted or terrain is on.
- Dropping a Favorite measure beside the globe or above the horizon is refused instead of landing on the horizon.
- Labels you have dragged into place now move with their graphic when you drag Layers Panel rows onto the map or duplicate a measure. Previously they stayed at the original spot.
- Image exports now include pin symbols. Previously pins exported as ordinary symbols.
- Pins in 3× and 4× image exports are drawn at full resolution instead of being capped at 2×.
- The active tool in the desktop toolbar is clearly highlighted again. In light mode the highlight had become almost white.
- The maximum map tilt is back to 60° (it was 85° in 1.6.0) because steeper tilts made the map slow.

### Under the hood

- Dependencies updated, including tactical-draw 0.10.1, the tactical-draw MapLibre adapter 0.7.0, and maplibre-gl 6.11.1.
