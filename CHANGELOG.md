# Changelog

What changed in each TacTrace release, newest first. Downloads are on the
[Releases](https://github.com/orbat-mapper/tactrace-public/releases) page.

## 1.12.1 - 2026-09-30

### Improvements

- ORBAT Mapper scenario import can bring in unit range rings: turn on **Include unit range rings** to add each unit's rings as circles, styled as they are in ORBAT Mapper.
- Pins scale better with the map. **Pin settings** has two new switches, **Shrink when zoomed out** and **Perspective sizing**, with sliders to tune them and a readout of the pin size at the current zoom. Both are on by default and never make a pin larger than its chosen symbol size.
- Orbit demo resumes turning sooner after you zoom in or out.

## 1.12.0 - 2026-09-30

### New

- **ORBAT Mapper scenario import**: open, drop or paste an ORBAT Mapper scenario (format 3.0.0 to 3.4.0) to bring it in as editable Layers. Pick a snapshot time or event, choose which sides and content to include, preview what will be imported, and place it on the **Active Page**, a **New Page** or a **New Map**. On the start page, **Import ORBAT Mapper scenario** opens it as a new Map, and you can also drop or paste a scenario there.

## 1.11.0 - 2026-09-28

### New

- **Replace icon**: the **Details Panel** and the mobile **Symbology** popover have a **Replace icon** button beside **Text amplifiers**. It opens the symbol library seeded with the selected symbol, and **Place** becomes **Replace**, swapping in the icon you pick. Picking an icon from another symbol set drops the modifiers and amplifiers that set can't show.

### Improvements

- **Favorites** in the symbol library now show your own favorites, one section per group, in place of the placeholder My Symbols collection. Favorite symbols select into the **Selected symbol** panel like Standard Symbols, and favorite control measures arm a draw like the **Control Measures** cards.
- The symbol library works better on phones. Cards are more compact (4, 3 or 2 columns for small, medium and large), and the selected-symbol panel is a resizable bottom sheet that opens as a one-row summary with **Place**. The jump buttons moved into a menu beside the symbol-set dropdown, so the search field keeps its width. Previously the cards fell to a single column and the panel could cover up to 60% of the screen.

## 1.10.0 - 2026-09-27

### New

- **Drag between tabs and windows**: drag an Item or Layer row from the **Layers Panel** into another TacTrace tab or window to drop a copy there. Items dropped on the map land centered on the drop point in the Active Layer; dropped on a Layer row they go into that Layer at their own location. A dropped Layer lands on top as the Active Layer. The original stays where it was, and the drop is one undo step. Like Paste, this works between tabs and windows of the same browser.
- **New control measures**: the Interdict mission task, drawn from a single centre point; the Bomb Area, Smoke, and Series or Group of Targets fire areas; the Unexploded Explosive Ordnance (UXO) Area; Ford Easy and Ford Difficult, drawn with three points where the third sets the width; and the Lane, Ferry and Raft Site protection lines.

### Improvements

- The desktop toolbar fits narrow map areas better. It stays centred while there is room and shifts over when there isn't, and if it still doesn't fit, **Measurement**, the laser pointer and orbit demo, and **Library** move into a **More tools** menu, as on phones. Previously the toolbar scrolled sideways as soon as the map area narrowed.
- With the **Details Panel** docked on the right, the map controls (compass, basemaps, place search and terrain) now stack beside the panel's edge. Previously they spread along the top of the map, where they could overlap the toolbar.

### Fixes

- The **Measurement** button in the desktop toolbar now shows as pressed while measuring.

### Under the hood

- Dependencies updated, including control-measures 0.30.0.

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
