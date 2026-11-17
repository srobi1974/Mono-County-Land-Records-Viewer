# Mono County Land Records Viewer

A browser-based map viewer (Leaflet) for Mono County land records: parcels, townships and sections, roads, record maps and scanned survey documents, with aerial imagery overlays.

Migrated from the Claude artifact "Mono County Land Records Viewer".

## Running it

The page loads its data with `fetch`, so serve it over HTTP rather than opening `index.html` directly:

```
python -m http.server 8000
```

Then open http://localhost:8000. It also works as a GitHub Pages site (Settings → Pages → deploy from the `main` branch).

## Migration notes

All data files and `index.html` are in place. `data/parcels.json` was re-exported from the QGIS layer "Tax Parcels with Owners" (27,207 parcels, WGS84) and keeps only APN, address, acres and legal description; owner and mailing fields are deliberately left out.

Imagery comes live from the USGS National Map orthoimagery tile service (`USGSImageryOnly`), so no image files are stored in this repo. The pre-cut aerial pictures used in the original artifact (`img/`, `data/imagery.json`) were dropped in favor of the tile layer.
