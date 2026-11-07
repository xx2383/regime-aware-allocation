# Regime-Aware Asset Allocation: A Robust Multi-Asset Tactical Overlay Framework

A walk-forward, machine-learning-driven market-regime detection framework applied to single-asset
timing (equities, bonds, USD) and multi-asset portfolio construction (equal-weight and
inverse-volatility weighting). The model combines a penalized K-Means jump model for regime
discovery with an XGBoost classifier for out-of-sample regime forecasting, selected each period
through a three-stage, cost-aware validation process (see [ALGORITHM.md](ALGORITHM.md)).

## Live signal

A daily-updated version of the SPX regime signal — current call, full history, and an interactive
backtest panel with adjustable lookback and window controls — is published at
**https://xx2383.github.io/spx-regime-signal/**.

## Repository structure

| File | Description |
|---|---|
| `result/SP500.ipynb` | Single-asset regime timing on the S&P 500 |
| `result/AGG.ipynb` | Single-asset regime timing on the Bloomberg U.S. Aggregate Bond Index |
| `result/USD.ipynb` | Single-asset regime timing on the U.S. Dollar Index |
| `result/MultiAssets.ipynb` | Equal-weight and inverse-volatility portfolios combining the three assets, rolling one-year returns, and the lookback-window analysis |
| `data/` | Exported position files for each asset (see [data/README.md](data/README.md)) |
| `ALGORITHM.md` | Description and pseudocode of the three-stage model-selection framework (images in `docs/`) |

## How to run

- **Figures and tables:** run Part 2 of each asset notebook, then `result/MultiAssets.ipynb`. They read the position files in `data/`. Figures are written to `result/figures/`; the performance, lookback, holding-period, tilt and cash-sensitivity tables are produced by the cells below each figure, and the saved outputs are already embedded in the notebooks.
- **Part 1 (training):** the training modules and the daily price data are not included in this repository, so Part 1 cannot be run from here.

## Disclaimer

This repository is a research and educational project. Nothing here is investment advice, and
past backtested performance is not indicative of future results. Do not use this code or its
outputs to make actual investment decisions without independent due diligence.
