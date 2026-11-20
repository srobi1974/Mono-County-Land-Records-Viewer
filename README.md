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

The page and data match the Claude artifact as of 2026-11-20 09:00 (artifact Version 151), including the Easements layer. `data/parcels.json` holds 27,207 tax parcels with only APN, address, acres and legal description; owner and mailing fields are deliberately left out.

Imagery comes live from the USGS National Map orthoimagery tile service (`USGSImageryOnly`), so no image files are stored in this repo. The pre-cut aerial pictures used in the original artifact (`img/`, `data/imagery.json`) were dropped in favor of the tile layer.
