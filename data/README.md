# Position data

Daily positions exported by Part 1 (training) of each asset notebook in `result/`.

| Folder | Files |
|---|---|
| `SP500/` | `SP500_Positions_raw.xlsx`, `SP500_Positions_5s.xlsx` |
| `BBG AGG BOND/` | `BBG_AGG_Positions_raw.xlsx`, `BBG_AGG_Positions_5s.xlsx` |
| `DBUSDX/` | `DBUSDX_Positions_raw.xlsx`, `DBUSDX_Positions_5s.xlsx` |

- `*_Positions_raw.xlsx`: the raw daily 0/1 regime forecast, lagged one day to avoid look-ahead (`{ASSET}_Position`), with the asset's price, daily return, the 3-month Treasury yield (`DGS3MO`, `rf_daily`) and the unlagged `Regime_Forecast`.
- `*_Positions_5s.xlsx`: the position after the five-day confirmation rule (the position changes only after the opposite raw signal has appeared on five consecutive days), with the daily return and `rf_daily`.

`vol_warmup_2007.csv` holds the volatility used for the inverse-volatility weights on every trading day of 2007: the 252-day rolling standard deviation of each asset's daily return (on the common trading calendar), lagged one day so that the weights set on a day never use that day's own return. It was computed with the price history before 2007 so that the weights are defined from the first day of the sample; the notebook uses it only to fill the first 252 rows of its own rolling volatility.

Price data are not included.
