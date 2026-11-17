# Mono County Land Records Viewer

A browser-based map viewer (Leaflet) for Mono County land records: parcels, townships and sections, roads, record maps and scanned survey documents, with aerial imagery overlays.

Migrated from the Claude artifact "Mono County Land Records Viewer".

## Running it

The page loads its data with `fetch`, so serve it over HTTP rather than opening `index.html` directly:

```
python -m http.server 8000
```

Then open http://localhost:8000. It also works as a GitHub Pages site (Settings → Pages → deploy from the `main` branch).

## Migration status — incomplete

All 29 data files and `index.html` are in place. `data/parcels.json` was re-exported from the QGIS layer "Tax Parcels with Owners" (27,207 parcels, WGS84) and keeps only APN, address, acres and legal description; owner and mailing fields are deliberately left out.

Still to be added:

- About 470 images under `img/` (town and county aerial tiles such as `img/county_*.jpg`, `img/mammoth_*.jpg`, plus the `img/rec_*.jpg` record tiles, about 200 MB total). Imagery overlays will show blank until these are added.

Copy those files from the original project folder into `data/` and `img/` with the same names and commit them. No single file exceeds GitHub's 100 MB limit.
