# Configuring TacTrace

You can change TacTrace's basemaps and disable its online place search and external basemap plugin without rebuilding the application.

## Where to put the configuration

### Website or downloaded website bundle

Edit `config/mapConfig.json` next to the application's `index.html`:

```text
index.html
config/
  mapConfig.json
```

Serve the folder through your web server and reload TacTrace after editing the JSON. If TacTrace is installed under a subdirectory, keep the configuration inside that installation's `config` folder. Keep a copy of your configuration when replacing the application with a newer release.

### Single-file HTML download

The single-file version contains its own defaults and starts with Blank. It does not automatically read a neighboring `mapConfig.json`.

Use **Load configuration…** on the start page, under **PMTiles** in the app menu, or in the command palette. Select your JSON file to apply it for the current session. Reopening the HTML restores its embedded defaults, so load your configuration again when needed.

**Load configuration…** also works in the website version. A reload returns to the configuration deployed on the web server.

## Example: a private map server

Save the following as `mapConfig.json`, replacing the tile address and attribution with those for your server:

```json
{
  "basemaps": [
    {
      "name": "local-topo",
      "title": "Local topographic map",
      "sourceType": "raster",
      "tiles": ["https://maps.example.org/topo/{z}/{x}/{y}.png"],
      "tileSize": 256,
      "maxZoom": 18,
      "attribution": "Local mapping service"
    }
  ],
  "features": {
    "basemapControl": false,
    "placeSearch": false
  }
}
```

This offers your map and Blank in TacTrace's existing basemap picker. The external plugin and online place search are disabled.

## Basemap list and defaults

The `basemaps` array replaces TacTrace's configured list. The shipped list contains Light, Streets, Dark, Satellite, and Blank. The plugin supplies its additional catalog, including Kartverket, separately when enabled; you do not need to copy those entries into this file.

- `name` is a unique, stable identifier. Keep it unchanged when updating an entry so saved selections continue to work. Do not use the reserved `archive-` prefix.
- `title` is the display label. If omitted, TacTrace displays `name`.
- The first entry is the default when there is no valid saved selection. A previously selected basemap takes precedence if it is still available.
- Blank is always available, even if omitted or if `basemaps` is empty. The identifier `blank` belongs to TacTrace's built-in white background.
- Configured entries appear in the existing picker and basemap menus. When the plugin is enabled, they also appear in its catalog and override plugin entries with the same identifier.
- Loading a configuration preserves your map content. Basemap preferences belong to the browser/device and are not stored in `.tactrace` files.

Use valid JSON: double-quoted keys and strings, no comments, and no trailing commas.

## Supported basemap sources

Add any of these entry types to the `basemaps` array.

### Raster tiles

Use an XYZ or TMS tile service:

```json
{
  "name": "local-imagery",
  "title": "Local imagery",
  "sourceType": "raster",
  "tiles": ["https://maps.example.org/imagery/{z}/{x}/{y}.jpg"],
  "tileSize": 256,
  "scheme": "xyz",
  "minZoom": 0,
  "maxZoom": 19,
  "attribution": "Imagery provider"
}
```

`tiles` must contain at least one URL. `tileSize` defaults to `256`; set it to match your service. Use `scheme: "tms"` for services with TMS row numbering. Zoom limits are optional and must be between 0 and 24.

### MapLibre style

Point to a MapLibre style JSON file:

```json
{
  "name": "local-vector",
  "title": "Local vector map",
  "sourceType": "style",
  "styleUrl": "https://maps.example.org/styles/topographic.json"
}
```

Alternatively, use an inline `style` object containing `version: 8`, `sources`, and `layers`. Supply exactly one of `styleUrl` or `style`.

### PMTiles archive served over HTTP

```json
{
  "name": "regional-map",
  "title": "Regional map",
  "sourceType": "pmtiles",
  "url": "https://maps.example.org/region.pmtiles",
  "flavor": "light"
}
```

The server must support HTTP byte-range requests. Vector archives use the Protomaps schema; other schemas may render incompletely. Vector themes (`flavor`) are `light`, `dark`, `white`, `black`, and `grayscale`. The default is `light`. For raster archives, an optional `opacity` between `0` and `1` controls transparency.

For an archive on your computer, use **PMTiles → Open PMTiles archive…** or drop the file onto the map. A disk path in the JSON does not grant the browser access to that file. Local PMTiles tools remain available when the external basemap plugin is disabled.

## Feature flags

Both flags default to `true` when omitted.

| Flag                      | Effect when set to `false`                                                                                                        |
| ------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| `features.basemapControl` | Disables the external basemap widget and its additional provider catalog. TacTrace's configured basemap picker remains available. |
| `features.placeSearch`    | Disables online place search and its requests. Coordinate entry remains available.                                                |

With the plugin disabled, choosing a configured basemap replaces the ordinary background. Any separately opened local PMTiles stack stays in place.

## URLs and hosting

For a configuration loaded automatically from a web server, relative URLs resolve against the configuration file's location. For example, `../maps/region.pmtiles` in `config/mapConfig.json` points to `maps/region.pmtiles` next to `index.html`. Tile placeholders such as `{z}`, `{x}`, and `{y}` are preserved.

For a configuration selected with **Load configuration…**, use absolute HTTP or HTTPS URLs. The browser cannot resolve resources relative to the selected file's directory on disk.

Use HTTPS map resources when serving TacTrace over HTTPS. A map server on another origin must allow browser access through CORS. A style can reference additional tile, font, and sprite URLs; those resources must also be reachable.

## Optional catalog metadata

Entries may include `provider`, `category`, `description`, and `tags`. To give a provider a display name, add a top-level `providers` array:

```json
"providers": [
  { "id": "local", "name": "Local maps" }
]
```

Then use `"provider": "local"` in the corresponding basemap entries. This fragment belongs inside the main configuration object, alongside `basemaps` and `features`.

## Offline use and troubleshooting

For disconnected use, open the single-file HTML, use Blank or local PMTiles files, and disable both feature flags. The website version still needs access to its application files when loaded.

The flags control those two features; configured maps can still make network requests. For a private-LAN setup, make sure all tiles, styles, fonts, and sprites are served within that LAN. A PMTiles URL is read from its server, not downloaded for later offline use.

If the configuration is missing or invalid, TacTrace shows an error and falls back to Blank with both feature flags disabled. Correct the deployed file and reload, or use **Load configuration…** to select a corrected file. An unreadable configured PMTiles archive is omitted with an error message.

If your new first entry is not selected after reloading, check whether TacTrace restored an existing selection. Choose your new map in the picker. If a map remains blank, check its resource URLs, server availability, CORS settings, and the browser's developer-console errors.
