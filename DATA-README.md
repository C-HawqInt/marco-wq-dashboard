# marco_wq_casts.csv: column guide

C-HAWQ dock water-quality casts, Marco Island, FL. One row per 0.5-ft depth bin per cast. The cast-level columns repeat on every row of that cast. The file contains site numbers, coordinates, dates and readings only. It has no names or addresses.

This file is produced by `Update-Dashboard.bat` (`build_dashboard.py`). Replace it with a newer copy rather than editing cells by hand.

| Column | Meaning |
|---|---|
| site | Map number for the location (stable all season) |
| latitude, longitude | Decimal degrees (WGS84) |
| date | Sampling date, YYYY-MM-DD |
| time | Cast start time, 24-hour local (EDT) |
| station | Only for a dock cast at two stations on the same day (e.g. Channel-Side / Inland-Side) |
| rating | From bottom dissolved oxygen: Healthy (5 mg/L and up), Some stress (2 to 5), Low oxygen (below 2) |
| surface_* / bottom_* | Average of readings within 0.5 m of the surface / of the deepest point reached |
| *_do_mgL | Salinity-adjusted dissolved oxygen, mg/L |
| *_saturation_pct | Dissolved oxygen, percent saturation |
| *_temp_F | Water temperature, degrees F |
| *_salinity_psu | Salinity, practical salinity units |
| max_depth_ft | Deepest point reached by the sonde, ft |
| tide_stage | Flood, Ebb, or Slack at the time of sampling |
| secchi_m | Secchi disk visibility, meters (blank if not measured) |
| water_color, clarity, weather | Field observations (clarity is a 1–10 rating) |
| depth_ft | Middle of the 0.5-ft depth bin, ft below the surface |
| do_mgL, saturation_pct, temp_F, salinity_psu | Bin-averaged readings at that depth |

Cleaning applied before export: out-of-water rows removed, depth zeroed at the surface, isolated sensor spikes removed (oxygen and salinity only), and first-immersion salinity lag trimmed. Thresholds: UF/IFAS Extension FA-27; Florida DEP Rule 62-302.533, F.A.C.
