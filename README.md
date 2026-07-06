# Italy Macro-Econometrics

Time series econometric analysis of Italian macroeconomic indicators using Gretl.


---

## Overview

Econometric analysis of Italy's macroeconomic performance using time-series data from the Federal Reserve Economic Data (FRED) database. The analysis examines GDP trends, market capitalization, and their interrelationships using classical econometric methods.

## Data Sources

| Dataset | Source | Description |
|---------|--------|-------------|
| `MKTGDPITA646NWDB` | FRED | Stock market capitalization to GDP ratio |
| `RGDPNAITA666NRUG` | FRED | Real GDP at constant national prices |

## Methodology

- Time-series stationarity tests (ADF, KPSS)
- Cointegration analysis
- OLS regression with diagnostic tests
- Heteroscedasticity and autocorrelation corrections

## Project Structure

```
├── data/
│   ├── MKTGDPITA646NWDB.csv    # Market cap to GDP ratio (FRED)
│   └── RGDPNAITA666NRUG.csv    # Real GDP series (FRED)
├── scripts/
│   ├── analysis_fixed.inp       # main script (corrected specification), use this one
│   └── analysis.inp             # Original version, kept for reference
└── LICENSE
```

## Usage

### Step 1, Build the Gretl dataset (one-time setup)

The scripts expect a Gretl data file `ItalyEconomy.gdt`, which is built from the CSVs in `data/`:

1. Open Gretl → **File → Open Data → User file** → select `data/RGDPNAITA666NRUG.csv` (annual frequency)
2. **File → Append Data** → select `data/MKTGDPITA646NWDB.csv`
3. **File → Save Data** → save as `ItalyEconomy.gdt` in the `scripts/` folder

### Step 2, Run the analysis

**GUI:** File → Open Script → `scripts/analysis_fixed.inp` → Run

**CLI:**
```bash
cd scripts
gretlcli -b analysis_fixed.inp
```

> `analysis_fixed.inp` is the corrected, current version. `analysis.inp` is the original submission, kept for reference.

## License

MIT License, see [LICENSE](LICENSE) for details.

## Author

**Mihretab Worku Morka**, [@mihretabworku](https://github.com/mihretabworku)
