# Changelog

What changed in each TacTrace release, newest first. Downloads are on the
[Releases](https://github.com/orbat-mapper/tactrace-public/releases) page.

## 1.25.0 - 2026-10-31

### New

- **Single envelopment** demo: a new FM 3-90 example on the start page, showing a force attacking along one flank of an enemy force.

### Improvements

- **Export as ORBAT Mapper scenario…** has more control over units, now grouped under **Units**: turn off **Export units** to export only control measures and shapes, turn off **Rotate units** to keep every unit upright, and turn off **Label units without T** so units made from symbols without a designation show no label in ORBAT Mapper, as on the map.
- **Copy to clipboard** in the ORBAT Mapper export keeps the dialog open, so you can copy again with other choices or also save the file.
- A globe button next to the compass switches between the flat map and the globe view.

### Under the hood

- Updated MapLibre GL JS to 6.16.

## 1.24.0 - 2026-10-29

### New

- **Export as ORBAT Mapper scenario…** in the File menu and command palette saves the current Page as an ORBAT Mapper scenario file, or copies it to the clipboard for ORBAT Mapper's **Paste from clipboard**. Each ORBAT becomes a side, with its units placed where their Linked Symbols stand and their overrides kept; a unit's other symbols come along as point symbols. Choose the start time, time zone, ORBATs and Layers to include, whether to leave out hidden content, and whether symbols not linked to a Unit become units of the side of their identity. Each Layer becomes an overlay of control measures and shapes, and importing the file back into TacTrace offers to reuse the ORBATs the Map already holds.

### Fixes

- Units imported from an ORBAT Mapper scenario now keep their rotation. Previously a rotated unit came in turned the wrong amount.

## 1.23.0 - 2026-10-29

### New

- **ORBATs**: keep orders of battle in the Map and place their units as symbols. The new **ORBAT** tab in the Workspace Sidebar creates ORBATs and shows each as a tree of Groups and Units that you can reorder by drag and drop and edit on a Unit's own page: name, short name, symbol, labels, reinforced/reduced status and fill color. On a phone the ORBAT opens as a drawer from **More tools** in the toolbar. Its **This Page** / **Whole Map** toggle shows the ORBATs this Page uses or every ORBAT in the Map.
- Drag a Unit from the ORBAT tab onto the map to place a Linked Symbol whose symbol code, name, designation and labels follow the Unit as you edit it. **Place with subordinates** places a Unit together with the Units under it, and **Fit to unit** zooms to where a Unit is placed. A Unit may be placed any number of times, on any Page.
- A Linked Symbol's **Details Panel** shows its Unit as a card with **Edit in ORBAT**, which opens the Unit's page in the ORBAT tab or drawer, and **Detach**, which removes the link and keeps exactly what the symbol shows. Selecting a Linked Symbol reveals and highlights its Unit in the ORBAT tab. A Unit is edited only in the ORBAT, and its labels in the **Text amplifiers** dialog.
- A Linked Symbol can override its Unit's status, task force and fill color in the **Overrides** block under the card, which adds one from **Override…** and shows each with the Unit's value and a reset. Its T, M, F, T2, G and H labels are overridden in the **Text amplifiers** dialog, each marked while it follows the Unit, with **Revert to unit** and **Revert all to unit**; an empty label override shows no label. Batch edit sets the same overrides across a selection.
- A Linked Symbol takes its Unit's fill color, else its Group's, else its ORBAT's, and the tree draws each Unit in that color.
- Drag a Unit or Group into another ORBAT to move it there, and its Linked Symbols on every Page follow. Drag plain symbols from the Details Panel onto an ORBAT to turn each into a new Unit, or onto the empty ORBAT tab to start a new ORBAT from them. A symbol without a designation stays without one once linked; turn on **No designation on symbols** on a Unit's page to keep any Unit's symbols unlabelled, as ORBAT Mapper does with an empty unique designation.
- On a phone or tablet, where there is no drag and drop, **Add to ORBAT…** in the Details Panel, the map's right-click menu and **More actions** makes the selected plain symbols wait in the ORBAT tab; tap a row to add them under it, **Add here** on an ORBAT to add them at its root, or the empty tab to start a new ORBAT. A tap on a Unit row only selects it; **Place on map** in the row menu arms it.
- Drag a Unit onto the map in another TacTrace window to place it there, linked when that Map holds the same ORBAT and unlinked otherwise. Drag a Unit or Group onto another window's ORBAT tab to copy it there with everything below it.
- The ORBAT tree's menus **Duplicate** a Unit, alone or with its subordinates, or a Group, and **Expand all** / **Collapse all** a branch or a whole ORBAT. Ctrl/Cmd-click and Shift-click select several rows to duplicate, delete, copy or drag together, Ctrl/Cmd-drag copies rows instead of moving them, and **Copy** / **Paste** (or Ctrl/Cmd+C/V) copy Units and Groups between ORBATs and windows. Dropping several selected Units on the map stacks them at the drop point.
- **Export…** in an ORBAT's menu saves it to its own file, **Export…** in the ORBAT tab's menu saves every ORBAT on show into one file, and **Import ORBAT file…** loads one into the Map, offering to reuse an ORBAT the Map already holds. Pick another Map's `.tactrace` file there to bring in every ORBAT it holds, without opening that Map. ORBAT Mapper scenario import brings in each side as an ORBAT with its groups, colors and labels: choose **ORBAT with Linked Symbols** to place its units too, or **ORBAT only**.
- **Import Data…** and dropping a file on the map also read an ORBAT exported from Battle Staff Tools (Spatial Illusions), including the ORBATs its Odin and SitaWare converters produce. It becomes a new ORBAT with the file's hierarchy, designations, labels, reinforced/reduced status and fill colors, and a stacked unit becomes that many Units.
- Deleting a Page that uses ORBATs asks what to do with them. Deleting a Unit, or removing an ORBAT from a Page, detaches its Linked Symbols instead of deleting them. ORBAT edits are undoable, and Linked Symbols survive copy and paste.
- **Highlight**: point the reader at a symbol, an axis of advance or an objective area, such as the main effort, in a fixed orange. It looks the same on every device and basemap and fades with the graphic's opacity.
- A highlighted symbol gets an orange glow around it, which takes the place of its Halo. Its labels keep their usual outline.
- A highlighted control measure or generic graphic gets a wider orange line beneath its stroke with a soft orange glow around it. An area is traced along its outline only, so its fill is unchanged, and a graphic with a transparent stroke is still traced.
- Turn Highlight on with the **Highlight** switch in the **Details Panel** (and in Quick Properties for symbols), the **Highlight** item in the map's right-click menu, or across a selection in batch edit.
- Highlights are saved in the Map. Favorites and Recents don't capture them, and a symbol linked to an ORBAT unit keeps its own.
- PNG, map-sheet PDF and KMZ exports draw Highlights. In map-sheet PDF and KMZ exports a symbol's glow is a little tighter than on the map.

### Improvements

- The **Includes** row in batch edit also has a chip for each Standard Identity in the selection, such as Friend or Hostile, so you can take, say, every hostile item out of the selection. Identity and kind chips combine, and the kind chips now show monochrome samples.
- Selecting several items now pans the map so they all clear the **Details Panel**, as a single selection already did.
- Halos are now a setting on this device instead of a switch on each symbol. **Settings → Halo** offers **Off**, **On** and **Auto**, the default, which draws a Halo on every symbol on dark and satellite basemaps and none on light or blank ones. The **Hard** and **Soft** styles are in the same menu. The Halo switch is gone from the Details Panel, Quick Properties and batch edit; older Maps with Halos switched on open as before, and the per-symbol Halo is no longer saved.
- A **Soft** Halo style draws a blurred glow around each symbol instead of the crisp **Hard** outline, with settings for its blur, spread, opacity, edge and color, and a thin outline of its own for labels.
- PNG and map-sheet PDF exports draw Halos as the map shows them. KMZ exports always draw Halos, so their **Add halos to all symbols** option is gone.

## 1.22.2 - 2026-10-24

### Improvements

- **New Map** now starts at the center and zoom of the last Map you worked in on this device, including from the start page. Exploring the Demo does not change it, and the first time you open TacTrace it still starts at the default view. A **New Page** starts at the current view.
- **Pin settings** has a **Size by echelon** switch. With it on, **Symbol size** is the size of a Battalion pin, and each By echelon symbol's pin is drawn at its echelon's ratio of that from the map's **Echelon sizes** table; Custom symbols keep the shared pin size. Image exports draw the same sizes.
- The **Echelon sizes** dialog has a **Symbols on this Page** section with a button that switches every unlocked symbol still at a Custom size to By echelon in one undoable step, without selecting them first.
- When a multi-selection mixes kinds of items, the **All** tab in batch edit ends with links to each kind's own tab, where settings such as **Size source** are.

### Fixes

- **Slope mobility**, **Landing sites** and **Landforms** are now offered for every area control measure, including those drawn only as lines, such as battle positions, strong points, Contain, Retain, Occupy, Secure, area and mobile defense, UXO areas and search areas. They cover the ground the graphic covers, not its teeth, arrows or other decoration.
- **Sightlines** are drawn under units shown as pins, so a line no longer crosses out the pin it ends at.

## 1.22.1 - 2026-10-23

### Improvements

- When a multi-selection mixes units, point control measures, control measures, images or annotations, the **Details Panel** has an **Includes** row with a chip for each, showing a sample symbol and how many are selected. Switch a chip off to take those items out of the selection, so Delete, Duplicate, Lock, Hide, the other commands in the panel's bottom row, and dragging the group leave them alone; switch it back on to select the same items again. Changing the selection any other way forgets the excluded items.

## 1.22.0 - 2026-10-23

### New

- **Size by echelon**: a symbol's **Size source** can now be **By echelon** instead of **Custom**, so it takes its size from the map's table of echelon sizes, from Team at 18 px up to Command at 60 px, and follows that table when its echelon or the table changes. Switch it with the **Custom | By echelon** toggle above the size control in the **Details Panel** and in batch edit. The **Echelon sizes** dialog, opened from **Settings**, the **Details Panel** or batch edit, edits each echelon's size in px or as a ratio, shows the sizes side by side at true size, sets the smallest size any echelon gets, and can make new placed and imported symbols start By echelon. The table is saved with the map, and a change to it is one undo step.

### Improvements

- **Reset size** now resets By echelon symbols to their echelon's size, so a set of units selected together come out at one scale, and it also works on a single selected symbol. A menu beside it resets at a map scale from 1:10,000 to 1:250,000 instead of the current view, so symbols sized in different sessions match and print at their table size at that scale. For a ground-scaled By echelon symbol, the **Details Panel** shows the size it draws at now, its full size, and the map scale it is full size at; batch edit says when the selected symbols are full size at different scales.
- **Reset size** and **Reset offset** now have their own icons instead of sharing one.

### Fixes

- The **m**/**px** switch beside a size in the **Details Panel** now clearly shows which unit is on in dark mode. Previously the selected unit was barely darker than the other.

## 1.21.0 - 2026-10-22

### New

- **Sightlines**: a terrain analysis on a point symbol that draws a line to every other symbol on the map within its reach, green where the ground leaves it clear and red where it blocks it, with an × on the crest that masks it. The analysis card lists each target with its distance and its clearance: how far above or below the sight line it stands. Set the observer and target heights, the reach, and which standard identities (and point control measures) it looks for. Lines follow the symbols as you drag them, a dragged observer can snap to the highest or lowest ground near the pointer as a viewshed's does, and hovering a target in the card outlines it on the map. The settings are saved with the map.

### Improvements

- An analysis's settings in the **Analysis** tab now open right beside its card. Previously they could open past the **Details Panel**, far from the card.

## 1.20.1 - 2026-10-22

### Improvements

- The **Tracked** profile in **Slope mobility** now marks slopes above 45% NO-GO, matching the severely restricted class for mechanized and armored forces in ATP 2-01.3 (Table B-2). Previously it used 60%. Maps saved with the old threshold keep it.

### Fixes

- A control measure dragged onto the map from **Graphics** or **Favorites** now shows its label at the normal size. Previously the label was too small to see until you resized the graphic, and the next one of that kind you drew had the same tiny label.

## 1.20.0 - 2026-10-22

### Improvements

- Control measures with labels now have a **Label size** control in the **Details Panel**, in batch edit and in the mobile **Appearance** popover.
- Selecting an item that the opening **Details Panel** would cover now pans the map, without zooming, until the item is clear of the panel.
- The **Details Panel** for a multi-selection leaves more room for its settings. Its bottom row is now a single row: Duplicate, Delete, Lock, Hide, **Reset size**, and a **More actions** menu with **Stacking order**, **Reset offset** and **Reset label positions**. **Opacity** sits with the other appearance settings.
- The **Details Panel** for a multi-selection no longer repeats "N of M selected" under every setting. A setting shows a small count, such as **6 of 13**, only when it doesn't apply to everything selected; hover it to see why. A switch whose items disagree now rests in the middle instead of looking off, and switches and choice rows mark disagreement with a **Mixed** badge. A slider whose items disagree shows no position until you set one.
- When a multi-selection mixes symbols, control measures and images, the **Details Panel** has a tab for each kind after **All**. **All** shows only the settings every selected item shares; a kind's tab shows that kind's full settings, and changes there apply to that kind only. The tabs stay in view while you scroll.
- The **Details Panel** for a single symbol or control measure leaves more room for its settings. Its bottom row is now a single row: Favorite, Duplicate, Delete, Lock, Hide, and a **More actions** menu with **Stacking order**. **Opacity** and **Terrain** now scroll with the other settings.
- The **Details Panel** for a single symbol or control measure now names its settings as the multi-selection panel does: **Frame visible** and **Fill visible** (in that order), **Symbol fill color**, **Adaptive monochrome**, and **Stroke color** or **Text color**.

### Fixes

- In the **Details Panel** for a multi-selection, each size now shows the unit it is actually in, and its m/px switch changes only that size. Previously a size in meters could show as px, a typed size could apply as meters to some graphics and as pixels to others, and switching one size's unit switched every size. When the selected items use different units for the same size, it gets one row per unit, labelled **(m)** or **(px)**.
- Hiding a control measure or image from the **Details Panel** now keeps the panel open on it, so you can show it again. Previously the panel closed. The same now holds when you hide every item in a multi-selection: its bottom row stays, and its eye button shows them again.
- Selecting another item now opens its **Details Panel** settings at the top. Previously they stayed scrolled to where the last item's were.
- A size slider in the **Details Panel** now always reaches the size it shows. Previously a size in meters could fall outside the slider's range at the current zoom, leaving the handle at one end while the field showed a different value.
- **Export image** now includes the terrain analyses shown on the map: viewshed, slope mobility, landing sites and landform shading, with their outlines, and the viewshed observer dots and range rings. Previously the exported image left them out.

## 1.19.4 - 2026-10-20

### Improvements

- The **Analysis Deck** has a **Snap area** button when the item has a viewshed. It sets how far from the pointer a dragged observer looks for high or low ground.
- The **Analysis** tab has an **Options** menu beside **Collapse all**, with **Smooth analysis edges** and **Viewshed snap area**. Previously these were only in **Settings › Terrain**.
- Labels on ground-scaled graphics now keep shrinking as you zoom out, then fade out and hide, instead of stopping at a minimum size and spilling outside their area.
- Area labels on screen-scaled control measures now shrink to fit inside their area as you zoom out, then fade out.

### Fixes

- With **Optimize map detail** on, labels in an image export now match their size on the map. Previously labels came out smaller than on screen.
- The OBJ HOVER and ASLT POS labels in the **FM 3-90 Tactics** demo now fit inside their areas.

### Under the hood

- Updated the tactical graphics engine to 0.18.

## 1.19.3 - 2026-10-20

### Improvements

- Type an exact size into the **Size** field above the size slider, in the unit shown (**m** or **px**). Typed sizes can go past the slider's 96 px, up to 512 px. The field also appears for other size sliders, such as a control measure's radius.

## 1.19.2 - 2026-10-20

### Fixes

- Switching a symbol's size from **m** to **px** now takes effect right away. Previously the symbol kept shrinking as you zoomed out, and resizing it with its transform box didn't change the symbol, until you switched page and back.

## 1.19.1 - 2026-10-19

### Improvements

- Terrain analyses are now saved with the map. Viewsheds, elevation profiles, slope mobility, landing sites and landforms, along with their settings, come back when you reopen the map. They are also copied when you paste or duplicate an item, layer or page. Starting, changing and closing an analysis can be undone. Showing or hiding one doesn't count as a change to the map.
- If the elevation data goes away, terrain analyses now wait for it to come back instead of closing. Each analysis card shows which elevation data it uses.
- The **Basemap** picker has an **Open PMTiles…** button for opening a PMTiles archive from your device.

### Fixes

- Notifications now follow dark mode. Previously their description text was dark grey on a dark background, which was hard to read.

## 1.19.0 - 2026-10-19

### New

- **Landforms**: shade the ground inside an area by its form: high ground (peaks, ridges, spurs) in brown, saddles in magenta, low ground (hollows, valleys, pits) in blue. Add it from the **Terrain** section of the **Details Panel** or the **Analysis** tab. **Lookup distance** sets the scale, from knolls to hills.

### Improvements

- Turn off **Smooth analysis edges** under **Settings → Terrain** to draw terrain analyses as crisp cells when zoomed in.
- Terrain analysis settings have help buttons explaining each setting.
- Observation post symbols can now take a **Fill color**.
- The **Viewshed** settings show **Detail** and the observer pin directly, no longer folded away.

## 1.18.0 - 2026-10-18

### New

- **Slope mobility**: shade the ground inside an area GO, SLOW-GO or NO-GO by slope. Turn it on in the **Terrain** section of the **Details Panel** and pick a **Wheeled**, **Tracked** or **Dismounted** profile, or set your own thresholds. The panel shows each class's share of the area. It considers slope only, not vegetation, soil, water or built-up areas.
- **Landing sites**: shade the ground inside an area where a helicopter can land, given a landing-point diameter and maximum slope (**Light**, **Medium** or **Heavy** profiles, or your own). The five largest sites are numbered on the map and listed in the panel; click one to centre on it. It sees slope only, not trees, wires or obstacles, so check the sites on imagery.
- **Analysis** tab: one card per item with its running terrain analyses, where you can hide, change or close each one and add more with **+**. **Profile comparison** overlays two or more elevation profiles, and **Combined coverage** shows the ground any viewshed sees. Open it from the measurement menu or with **Open in Analysis** in the **Details Panel**; on a phone it opens as a bottom sheet.

### Improvements

- Every **Viewshed** now runs on an item: click a symbol with the **Viewshed** tool, or drag on open ground to draw a circle with a viewshed. Circles can have a viewshed like Sectors, and a Sector's **Range fan** is now called **Viewshed**. Standalone viewsheds and **Keep as Item** are gone.
- Viewshed settings now live on the item's card in the **Analysis** tab, and the **Viewshed** deck is replaced by a bar at the foot of the map showing the selected item's terrain analyses. **Viewshed snap area** moved to **Settings → Terrain**.
- Dragging a symbol, Sector or circle with a viewshed redraws it as it moves and snaps to the highest or lowest ground (hold Alt, or Alt+Shift for the lowest).
- Several elevation profiles can be open at once, any terrain analysis can be hidden without closing it, and undoing an item's delete restores its analyses.
- Analysis cards show the cell size and warn when it is too coarse.
- On a phone, the **Terrain** section shows in an item's details, and the analysis bar scrolls sideways.
- The **Graphics** tab has a **Generic** filter for lines, arrows, rectangles, circles, Sectors and the like.

### Fixes

- Zooming to a circle now shows all of it, and zooming to a symbol with a viewshed frames the whole viewshed.
- On a touch screen, dragging a small symbol now moves it instead of scaling it.

## 1.17.4 - 2026-10-16

### Improvements

- The **Viewshed** observer can snap to a summit or a pit while you drag it. Turn it on with the **Snap to the highest ground** or **Snap to the lowest ground** button on the **Viewshed** deck, and press it again to turn it off. Or hold Alt during a drag to snap that drag to the highest ground (Alt+Shift for the lowest). **Snap area** in the **Viewshed** settings sets how far around the pointer it searches, from 8 to 96 screen pixels. A ring shows the ground searched, and the ground height shows under the observer while you drag.
- The **Viewshed** settings are more compact: observer height, target height and reach each fit on one row, and detail, snap area and the pin are folded away under a disclosure.
- The **Viewshed** settings button shows each value with an icon, names it on hover, and includes the cell size the viewshed was computed at. Clicking the cell size opens the settings at the detail level.
- The **Terrain** toggle is now on the map on phones and small screens too.

## 1.17.3 - 2026-10-15

### Improvements

- The **Measurement** button in the toolbar is now a split button, like **Annotations** and **Presentation tools**: the main half starts the measurement you used last (**Distance**, **Area** or **Viewshed**), and the arrow opens the menu. The **R** hotkey also starts the last-used measurement, **Distance** by default. Previously the button only opened the menu, and **R** started nothing.
- The **Viewshed** observer height can be **Above ground** or **Above sea level**, so a drone or aircraft keeps its altitude wherever you move it. Its pin stands at that altitude and reads e.g. "600 m ASL".
- **Measure the range from the eye** in the **Viewshed** settings treats the radius as slant range, the way a sensor or radio reaches. Ground beyond that range still blocks the view behind it. A **Range fan**'s minimum range is still measured along the ground.

### Fixes

- When several control measures are selected, the selection box now follows them as you pan the map. Previously it stayed where it was on screen unless the selection also included a unit ([#1](https://github.com/orbat-mapper/tactrace-public/issues/1)).
- Pressing Escape with several items selected now clears the selection. Previously the selection box disappeared but the **Details Panel** stayed open, still showing the items as selected.

## 1.17.2 - 2026-10-15

### Improvements

- **Hellfire** is now off by default. Turn it on with **Settings → Advanced → Enable Hellfire**, where its **On impact** choice now lives too. Until then it is left out of the presentation tools, the Orbit demo hint and the keyboard shortcuts list.
- MilX symbols that TacTrace has no icon for now import as a bare frame. Previously they were skipped.
- TacTrace starts faster: the **Viewshed** loads the first time you use it.

### Under the hood

- Updated dependencies, including MapLibre GL JS 6.14.

## 1.17.1 - 2026-10-13

### Improvements

- **Viewshed** (experimental): place several observers at once, one per click. Their coverage is combined so you can see which ground is seen by many, few or none, or you can show each one separately.
- **Dead ground** in the **Viewshed** highlights in red the ground no observer can see.
- The **Viewshed** deck is more compact: its settings now open from a single button.
- Several Sectors can show their **Range fan** (experimental) at the same time.
- Sectors can be rotated with a handle, and open toward the cursor as you draw them.

## 1.17.0 - 2026-10-12

### New

- **Range fan** (experimental): a selected Sector offers **Range fan** in the **Details Panel**'s **Terrain** section. It shows the viewshed from the Sector's anchor, cut to its arc and its inner and outer ranges, so you see only the ground a weapon or sensor can actually see within its sector of fire. Terrain outside the fan still blocks the view into it. The fan follows the Sector while you edit it and closes when the Sector is deleted.
- **Masking height** in the **Viewshed**: switch the deck from the visible ground to how high a target must rise to be seen, in bands from 0 to 500 m and above, with a legend above the deck.

### Improvements

- The **Viewshed** reaches up to 200 km, with detail levels from **Draft** to **Extreme**. A spinner shows while it computes, and the deck no longer shifts as results arrive.
- The **Viewshed** observer can stand as a pin at eye height, which is easier to see on a tilted map.
- Dragging the **Viewshed** observer over 3D terrain is smoother, and the shading keeps up with the pointer. The outline is drawn once you let go.
- The **Elevation profile** of a control measure now follows the line while you edit it. Previously it updated only once the edit ended.

## 1.16.0 - 2026-10-11

### New

- **Viewshed** (experimental): a terrain tool (hotkey **W**, in the **Measurement** menu) that shows what can be seen from a point. Click the map to place an observer, and the ground visible from there within a radius is shaded and outlined. Drag the observer to move it, and choose **Standard**, **Fine** or **Max** detail; the deck shows the resulting cell size. It needs elevation data, and nothing is saved to the Map File.
- **Elevation profile** (experimental): show the ground elevation along a kept distance measurement or a line control measure as a chart, with a marker on the line that follows the chart. Turn it on with **Elevation profile** in the **Details Panel** or in the measurement deck. Nothing is saved to the Map File.

### Fixes

- PMTiles basemaps and elevation archives work again in the single-file download. Previously they never rendered when the file was opened from disk.

## 1.15.0 - 2026-10-11

### New

- **Hellfire**: a presentation tool (hotkey **F**) next to the laser pointer and the Orbit demo. Click the map to fire a Hellfire missile, or Shift+click while orbiting. Choose what happens to Icon-based Symbols caught in the blast under **Settings → Hellfire → On impact**: nothing, hide them, delete them, or set their status to destroyed. The impact is one step you can undo, and Locked symbols are spared.

### Improvements

- Rows in the **Layers** panel now show a preview of each item: Icon-based Symbols show their symbol, and control measures show a small drawing of their kind.
- ORBAT Mapper scenario import accepts scenarios in format 3.7.0 without the newer-format warning, and brings in their point control measures, such as checkpoints, as Icon-based Symbols with their size, rotation and text.
- Imported units are hidden or locked only when they or their side group are, as in current ORBAT Mapper. Previously a hidden or locked unit also hid or locked its subordinates.
- The Orbit demo shows a short hint when it starts, and the keyboard shortcuts list includes Shift+click to fire Hellfire.

### Fixes

- Control measures imported from ORBAT Mapper with a size in meters now keep that size. Previously they came in sized in pixels instead.

### Under the hood

- Updated dependencies, including MapLibre GL JS 6.13.

## 1.14.0 - 2026-10-06

### New

- **Offline terrain**: 3D terrain and hillshading can now read elevation data from an elevation archive, a PMTiles archive of elevation tiles such as an extract of Mapterhorn. Choose **Terrain → Open elevation archive…**, drop the archive on the map and choose **Use for terrain**, or add an archive's address in **PMTiles basemaps…** with **Elevation archive** checked. The archive replaces the online elevation data while it is in use, and supported browsers reopen it next time.

### Improvements

- The single-file download no longer reads elevation data from the internet by itself. Its terrain button offers a choice between online elevation data and an elevation archive, and remembers it.
- While drawing a control measure, the **Details Panel** now also offers **Filled**, **Echelon**, **Mine type** and **Open** where the measure has them, so you can set them before placing any points.
- The **Filled**, **Echelon** and **Mine type** you last chose carry over to the next control measure you draw, like the **Smooth** and **Arrowhead style** choices. A measure that doesn't offer the remembered choice starts with its own default instead.
- Picking a different control measure while drawing now switches to it straight away, discarding the unfinished one. Previously the pick was ignored until you finished or cancelled the drawing.
- ORBAT Mapper scenario import accepts scenarios from the current ORBAT Mapper (format 3.5.0 and 3.6.0). Scenarios from an even newer version are still imported, with a warning that some content may be missing or imported incorrectly.
- Imported range rings respect ORBAT Mapper's range ring visibility: rings in a hidden range ring group, and rings hidden with ORBAT Mapper's options to hide all or ungrouped range rings, come in hidden.

### Fixes

- Classic Arrows in ORBAT Mapper scenarios saved before format 3.5.0 now import pointing the right way. Previously they came in back to front.

## 1.13.0 - 2026-10-03

### New

- **MilX import**: open or drop map.army MilX layer files (`.milxly` and `.milxlyz`) through **Import Data**, onto the map, or on the start page. Tactical symbols come in with their symbology, and free-format lines, areas, Bézier curves, rectangles, circles and text labels become editable Generic Graphics with their colors, fill and designation. A symbol size slider with a ground/screen toggle sets how big imported symbols are, and graphics TacTrace has no equivalent for are listed instead of being silently dropped.

### Improvements

- **Bézier smoothing** for Generic Graphic lines and areas and for the Classic Arrow shaft: alongside **Curve**, the **Smooth** options now offer **Bézier**, which shapes the line from its points as a control frame instead of passing through every point.
- Generic Graphics (line, area, rectangle, circle, sector) and the Classic Arrow can carry a designation (T) label. Areas center it inside the shape; lines and arrows place it above the middle, reading along the line. Drag it to move it, and use the label size control to resize it.
- Classic Arrow heads keep the same size whatever the length of the arrow. Drag the new handle on the head's corner to change its length and width, or Alt+click it to restore the default size.
- When drawing a **Classic Arrow**, the first click now places the arrow tip, as it does for the other arrows. Classic Arrows in existing Maps are updated when opened and keep pointing the same way. Maps saved by this version can't be opened in older versions of TacTrace.
- Right-to-left map labels (such as Arabic and Hebrew) are now drawn by the map itself instead of a separate plugin, so nothing extra is downloaded for them. Labels in complex scripts such as Devanagari and Khmer are now also drawn correctly.
- Opening Maps and importing files with many tactical graphics is faster.
- The **Annotations** menu now offers **Arrow**, which draws a Classic Arrow. While drawing a Classic Arrow or Block Arrow, the **Details Panel** shows **Arrowhead style**, so you can pick the head before placing any points.
- The **Smooth** style (**Curve**, **Bézier** or **Rounded**) and the **Arrowhead style** you last chose carry over to the next graphic you draw, whether you chose them while drawing or while editing an existing graphic. A graphic that doesn't offer the remembered style starts with its own default instead.
- Turning on terrain with the map's terrain button tilts a top-down view so the relief is visible, and turning it off levels the camera again.

### Fixes

- The orbit demo keeps the camera at a steady height over hilly terrain. Previously it rose and fell with the ground under the map center.

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
