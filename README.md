# EV Model Compare — open dataset

Exported: 2026-09-24.

This dataset contains electric vehicle specifications, field sources, recall
campaign identifiers, and US state charging information.

| File | Rows | Contents |
| --- | ---: | --- |
| `data/ev_models.csv` | 40 | One vehicle model per row |
| `data/ev_models.json` | 40 | The same vehicle model records |
| `data/sources.csv` | 987 | Sources for individual vehicle fields |
| `data/recalls.csv` | 75 | NHTSA campaign identifiers and links |
| `data/us_states_charging.csv` | 51 | Residential rates and DC fast charging by state |

## Column dictionary

- `slug`, `name`, `url`: model identifier, display name, and page URL.
- `model_year`, `body_style`, `seats`, `curb_weight_kg`: vehicle basics.
- `sold_in_us`, `sold_in_eu`: market availability booleans.
- `battery_*`: battery chemistry, construction, capacity, supplier, thermal
  management, and voltage.
- `range_*`, `efficiency_*`: driving range and energy consumption under the
  named test cycle or real-world estimate.
- `dc_*`, `ac_onboard_kw`, `v2l_kw`: charging and power export specifications.
- `power_kw`, `torque_nm`, `accel_*`, `top_speed_kmh`: performance.
- `msrp_*`: listed prices in the named currency.
- `warranty_*`, `nhtsa_overall_stars`, `euroncap_*`, `recall_count`:
  warranty and safety information.
- `est_*`: modelled estimates; see
  https://evmodelcompare.com/methodology/.
- `sources.csv`: `slug`, `field`, `source`, `url`, `as_of`.
- `recalls.csv`: `slug`, `campaign_id`, `nhtsa_url`.
- `us_states_charging.csv`: state code/name, residential electricity rate,
  cheapest-rate rank, monthly home charging cost for a median EPA car driven
  1,125 miles/month, page URL, DC fast sites and plugs, network, and connector
  site counts.

For numeric vehicle fields, 0/blank = not stated. JSON uses `null` for
unstated numeric values.

## Sources

EPA fueleconomy.gov; manufacturer specification and warranty documents;
NHTSA; EIA Electric Power Monthly Table 5.6.A, June 2026; and DOE AFDC
station locator, pulled 2026-09-16.
Individual vehicle field sources appear in `data/sources.csv`.

Cite as: EV Model Compare (2026). Open EV dataset.
https://evmodelcompare.com/

License: CC BY 4.0. Attribution example: "EV specifications from EV Model
Compare, https://evmodelcompare.com/ (CC BY 4.0)."
