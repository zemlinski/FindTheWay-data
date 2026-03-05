# FindTheWay Data 🗺️

This repository hosts pre-generated trail data and map-related resources for the **FindTheWay** Android application.

## Contents

- `/trails`: GeoJSON files containing colored hiking trails for various European countries (Poland, Czechia, Slovakia, etc.).
- `/styles`: Custom MapLibre map styles and sprite definitions.

## Data Source & Attribution

Data for hiking trails is extracted from **OpenStreetMap (OSM)** via the Overpass API.

- **Data © OpenStreetMap contributors**
- Trails are rendered based on the `osmc:symbol` tagging schema.
- Map tiles are served via MapLibre/MapTiler or other providers as configured in the app.

## License

- **Data:** All GeoJSON files in this repository are derived from OpenStreetMap data and are licensed under the [Open Database License (ODbL) v1.0](https://opendatacommons.org/licenses/odbl/1-0/).
- **Code:** Any scripts or configuration files in this repository are licensed under the **MIT License**.

---
*Generated with ❤️ for hikers and explorers.*
