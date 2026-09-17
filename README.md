# Data for the FIN 6040 pandas exercises (Financial Modeling, Yeshiva University, Fall 2026)

Four CSV files used by the course's five pandas notebooks. One row per US-listed company: fiscal-2025
financial statement items (Compustat) plus the 2025 stock return, volatility and beta (CRSP), for
companies above $1B of market value (`companies_2025.csv`), the $300M-$1B firms (`small_caps_2025.csv`),
last year's fundamentals with raw Compustat names (`fundamentals_2024.csv`), and GICS industry names
(`gics_industries.csv`). See `data_dictionary.md` for every column.

Load in Python:

```python
import pandas as pd
DATA_URL = "https://raw.githubusercontent.com/assacohen1/fin6040-pandas-data/main/"
firms = pd.read_csv(DATA_URL + "companies_2025.csv")
```

Source: Wharton Research Data Services (Compustat North America, CRSP). For classroom use.
