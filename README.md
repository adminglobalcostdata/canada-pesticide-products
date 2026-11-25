# Canada Pesticide Products: 84,741 records, ARLA PPID

[![Apify Actor](https://img.shields.io/badge/Apify-Actor-1f6feb)](https://apify.com/phonic_lily/canada-pesticide-products) ![Licence](https://img.shields.io/badge/licence-Open_Government_Licence_Canada-blue) ![Records](https://img.shields.io/badge/records-84%2C996-green)

Search 84,741 records from Health Canada's Pesticide Product Information Database: 21,860 registered and historical pesticide products and 62,881 registration applications, with active ingredients and CAS numbers, registrant, status, use sites and pests. Embedded data, no scraping, pay per record.

## What you get
- **84,996 records**, each carrying its own `license` and `attribution` fields, ready to republish with the required credit.
- A **100-record free sample** in this repository: [`sample.jsonl`](sample.jsonl) and [`sample.csv`](sample.csv) (opens as a table on GitHub).
- The **full dataset** as a filterable API (JSON, CSV, Excel), no scraping, no login: [Canada Pesticide Products: 84,741 records, ARLA PPID on Apify](https://apify.com/phonic_lily/canada-pesticide-products).

## One record
```json
{
  "record_id": "product-28103.01",
  "record_type": "product",
  "application_number": null,
  "registration_number": "28103.01",
  "product_name_en": "(PLUS GREEN) ELIMINATOR PLUS ANT KILLER INSECTICIDE",
  "product_name_fr": "ÉLIMINATEUR PLUS (PLUS VERT) INSECTICIDE POUR ÉLIMINER LES FOURMIS",
  "registration_status": "Cancelled",
  "marketing_type": "DOMESTIC",
  "product_type": "INSECTICIDE",
  "registrant": "GROUPE BMR INC.",
  "active_ingredients": [
    "SILICON DIOXIDE (PRESENT AS 100% DIATOMACEOUS EARTH) - FRESH WATER FOSSILS"
  ],
  "active_ingredient_cas": [
    "61790-53-2"
  ]
}
```

## Quick start
Python:
```python
from apify_client import ApifyClient
client = ApifyClient('<YOUR_APIFY_TOKEN>')
run = client.actor('phonic_lily/canada-pesticide-products').call(run_input={'maxResults': 10})
for item in client.dataset(run['defaultDatasetId']).iterate_items():
    print(item)
```
Or from the command line:
```bash
curl -X POST 'https://api.apify.com/v2/acts/phonic_lily~canada-pesticide-products/run-sync-get-dataset-items?token=<YOUR_APIFY_TOKEN>' \
  -H 'Content-Type: application/json' -d '{"maxResults": 10}'
```
Pricing is pay-per-record on Apify (see the Actor page); the sample here is free.

## Fields
| Field | Description |
|---|---|
| `record_id` | Stable id: product-<registration number> or application-<application number>. |
| `record_type` | product or application. |
| `application_number` | Application number (applications only). |
| `registration_number` | Pesticide registration number. |
| `product_name_en` | Product name (English), null if confidential. |
| `product_name_fr` | Product name (French), null if absent. |
| `registration_status` | Registration status. |
| `marketing_type` | Marketing type (commercial, domestic, technical active...). |
| `product_type` | Product type (herbicide, insecticide...). |
| `registrant` | Registrant company. |
| `active_ingredients` | Active ingredients (English). |
| `active_ingredient_cas` | CAS numbers aligned with active_ingredients, null where unknown. |
| `date_first_registered` | First registration date (products). |
| `exclusive_period_start` | Exclusive period start date (products). |
| `expiry_date` | Registration expiry date (products). |
| `use_site_categories` | Use site categories (products). |
| `sites_of_use` | Sites of use (products). |
| `pests` | Pests or targets (products). |
| `date_received` | Application received date (applications). |
| `outcome` | Application outcome (applications). |
| `purpose` | Application purpose (applications). |
| `category` | Application category (applications). |
| `current_or_historical` | Current or Historical. |

## Data, licence and attribution
Health Canada, Pest Management Regulatory Agency (PMRA/ARLA), Pesticide Product Information Database, Open Government portal dataset e10b0d6e-04ac-4014-a64a-666c3874bbe0 (https://open.canada.ca/data/en/dataset/e10b0d6e-04ac-4014-a64a-666c3874bbe0), licence Open Government Licence - Canada (https://open.canada.ca/en/open-government-licence-canada). Built from the official product and application extracts (https://pest-control.canada.ca/pesticide-registry-api/api/extract/product and /application); CAS numbers joined from the ingredient extract by active ingredient name. Names flagged 'Confidential' by the source are returned as null. Empty values are null, never 0. Registrants are companies. This is not official Health Canada data service and does not imply endorsement; verify registrations with the PMRA before relying on them.

**Licence:** Open Government Licence - Canada (version 2.0)

**Attribution:** Contains information licensed under the Open Government Licence - Canada. Source: Health Canada, Pest Management Regulatory Agency, Pesticide Product Information Database.

Snapshot date: 2026-11-25. Empty values are `null`, never 0.

## Cite this dataset
GitHub's *Cite this repository* button reads [`CITATION.cff`](CITATION.cff).

## Feedback
Found an error or want a field added? Open an issue in this repository.
