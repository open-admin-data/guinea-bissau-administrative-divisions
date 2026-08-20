# Guinea-Bissau Administrative Divisions / Guiné-Bissau



## Overview

| Item | Details |
|------|---------|
| Region | 9 |
| Sector | 39 |
| Tabanca | 3,905 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-08-20 |
| Website | [openadmindata.org/gw](https://openadmindata.org/gw/) |
| API | [openadmindata.org/api/gw](https://openadmindata.org/api/gw/) |
| Flag | [PNG](https://onlygames.me/flags-png/gw/) · [SVG](https://onlygames.me/flags-svg/gw/) · [PDF](https://onlygames.me/flags-pdf/gw/) |
| National Anthem | [🎵 Listen & Download Guinea-Bissau National Anthem MP3](https://onlygames.me/national-anthems/gw/) |

## Browse by Region

| # | Region | Sectors | Tabancas | Link |
|---|----|----|----|------|
| 1 | Bolama/Bijagos | 4 | 248 | [Browse](divisions/bolamabijagos-gw03/) |
| 2 | Tombali | 5 | 425 | [Browse](divisions/tombali-gw09/) |
| 3 | Bissau | 1 | 0 | [Browse](divisions/bissau-gw08/) |
| 4 | Quinara | 4 | 220 | [Browse](divisions/quinara-gw07/) |
| 5 | Biombo | 3 | 164 | [Browse](divisions/biombo-gw02/) |
| 6 | Cacheu | 6 | 651 | [Browse](divisions/cacheu-gw04/) |
| 7 | Gabu | 5 | 574 | [Browse](divisions/gabu-gw05/) |
| 8 | Bafata | 6 | 801 | [Browse](divisions/bafata-gw01/) |
| 9 | Oio | 5 | 822 | [Browse](divisions/oio-gw06/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-region.json](data/all-region.json) | JSON | All 9 region records |
| [all-sector.json](data/all-sector.json) | JSON | All 39 sector records |
| [all-tabanca.json](data/all-tabanca.json) | JSON | All 3,905 tabanca records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-2 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-region.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['sector']} sectors")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-region.json", "utf-8"));
console.log(`Total: ${data.length} regions`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=region, 2=sector, 3=tabanca |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{region-slug}/
divisions/{region-slug}/{sector-slug}/
```

Tabancas are listed inline in each sector's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-region links
- [Per-region data](docs/llms-full/) — Full data by region

## Citation

```
Guinea-Bissau Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/guinea-bissau-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
