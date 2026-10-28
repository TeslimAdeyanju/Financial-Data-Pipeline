# Financial Data Pipeline and Market Analytics

> A modular financial data engineering project that integrates economic indicators and market data for reproducible analysis, with forecasting and strategy evaluation planned for later phases.

**Status:** Data extraction, saved research datasets and exploratory notebooks present. Forecasting, automated pipelines and trading backtests are future development stages.  
**Current tools:** Python, pandas, NumPy, yfinance, pandas-datareader, Matplotlib and Plotly.

## Executive Summary

Financial decision-making often depends on combining market prices with macroeconomic information from different sources. This project develops a structured research workflow for acquiring, validating, visualising and analysing those datasets.

The current repository contains an extraction and setup notebook, an exploratory analysis notebook and locally saved datasets for equity indices and United States macroeconomic indicators. It is a foundation for future forecasting and strategy research, rather than a completed end-to-end automated trading system.

## Business and Analytical Objectives

The project aims to create a reliable analytical base for studying how financial markets interact with growth, inflation and interest rates.

1. Collect data from appropriate market and economic sources.
2. Standardise time indexes, units and update frequencies.
3. Explore trends, growth rates and changes in market performance.
4. Assess coverage, missing values and consistency before modelling.
5. Develop predictive features and evaluate models on temporally valid splits in a later phase.
6. Extend the research to simulations and scheduled reporting when the foundations have been validated.

## Data Sources and Current Coverage

The first notebook, `Note 1-Data Extraction and Setup/note-1-data-extraction-and-Setup.ipynb`, includes code using Yahoo Finance and Federal Reserve Economic Data (FRED). The repository contains saved CSV files for selected datasets.

| Data | Example files | Analysis |
| --- | --- | --- |
| Potential real GDP | `gdppot.csv` | Growth and macroeconomic trends |
| Consumer prices | `df_cpi.csv` | Inflation patterns |
| Federal funds rate | `fedfunds.csv` | Monetary policy context |
| S&P 500 | `spx_index.csv`, `snp500_daily_non_delayed.csv` | Equity market performance |
| DAX index | `dax_daily.csv` | German equity market analysis |
| Combined macro indicators | `macro_data.csv` | Multi-variable macroeconomic research |

The second notebook, `Note 2-Exploratory Data Analysis/note.ipynb`, explores IPO-related data and additional research steps. Source conventions, dates, adjustments, provenance and licensing must be verified before external distribution.

## Workflow

```mermaid
flowchart LR
 A[FRED and market data sources] --> B[Python extraction]
 B --> C[Data cleaning and validation]
 C --> D[Saved CSV datasets]
 D --> E[Exploratory financial analysis]
 E --> F[Growth and trend visualisation]
 F --> G[Future feature engineering and forecasting]
```

The current implementation is notebook-based and saves or loads intermediate CSV files. The later forecasting and automation stages in the project roadmap are **not currently implemented as a complete production pipeline**.

## Implemented Analysis

The first notebook includes:

- Configurable data collection and download helper functions with retry handling.
- Analysis of potential GDP and growth rates.
- Core CPI and inflation-related transformations.
- Federal funds rate examination.
- Equity index data retrieval, plotting and comparisons.
- Data summaries and validation-oriented checks.

The second notebook provides additional exploratory work, including IPO-related data handling.

## Development Roadmap

| Phase | Scope | Status |
| --- | --- | --- |
| 1. Source and acquire data | Market and macroeconomic extraction | Notebook implementation present |
| 2. Explore financial data | Trends, descriptive analysis and initial validation | In progress |
| 3. Engineer predictive variables | Lag features, technical indicators and target construction | Planned |
| 4. Forecast and evaluate | Time-series or classification modelling with temporal holdouts | Planned |
| 5. Simulate strategies | Transaction costs, returns, drawdown and benchmark testing | Planned |
| 6. Automate | Scheduled ingestion, monitoring and reporting | Planned |

No trading performance, forecast accuracy or operational automation benefits are claimed in the absence of a reproducible implementation.

## Repository Structure

```text
README.md
pyproject.toml
uv.lock
Note 1-Data Extraction and Setup/
    note-1-data-extraction-and-Setup.ipynb
    gdppot.csv
    df_cpi.csv
    fedfunds.csv
    spx_index.csv
    snp500_daily_non_delayed.csv
    dax_daily.csv
    macro_data.csv
Note 2-Exploratory Data Analysis/
    note.ipynb
docs/
    legacy-readme.md
```

## Installation and Reproducibility

The repository uses `pyproject.toml` and `uv.lock`, not the `requirements.txt` referenced by the old README.

```bash
git clone https://github.com/TeslimAdeyanju/Financial-Data-Pipeline.git
cd Financial-Data-Pipeline
uv sync
uv run jupyter lab
```

The project manifest specifies Python 3.13 or newer. Some notebook cells use relative CSV paths and may need to run from the corresponding notebook folder; others require internet access and compatible upstream APIs. The setup has not been independently executed in a clean environment.

## Quality Controls and Limitations

- Align mixed market trading calendars and macroeconomic reporting frequencies before merging datasets.
- Guard against look-ahead bias, revised economic releases and data leakage in future models.
- Record dates, transformations, adjusted-price treatment and units for every source.
- Avoid presenting saved market data as live quotes.
- Add repeatable tests for source availability, nulls, duplicate dates and schema changes.
- Modularise notebook code before introducing scheduled automation.
- Respect provider licences and restrictions on redistribution.

## Next Steps

Prioritise a reproducible data dictionary and ingestion workflow, then build consistent merged datasets and documented exploratory findings. Only after these controls are in place should forecasting benchmarks, backtesting and scheduling be introduced.

## Author

**Teslim Adeyanju**  
[GitHub](https://github.com/TeslimAdeyanju) | [Portfolio](https://adeyanjuteslim.co.uk) | [LinkedIn](https://www.linkedin.com/in/adeyanjuteslimuthman)

[Original README archive](docs/legacy-readme.md)
