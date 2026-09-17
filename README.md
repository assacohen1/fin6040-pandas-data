# FIN 6040 pandas exercises (Financial Modeling, Yeshiva University, Fall 2026)

Five notebooks that teach pandas on real financial data, in the order of the Kaggle *Pandas* course.
One question runs through all of them: **what makes a stock risky?**

Open a notebook directly in Google Colab:

| # | Notebook | Kaggle lesson |
|---|---|---|
| 1 | [Reading data, selecting rows and columns](https://colab.research.google.com/github/assacohen1/fin6040-pandas-data/blob/main/notebooks/01_indexing_selecting_assigning.ipynb) | Indexing, selecting & assigning |
| 2 | [Summary statistics, ratios and transforming columns](https://colab.research.google.com/github/assacohen1/fin6040-pandas-data/blob/main/notebooks/02_summary_functions_and_maps.ipynb) | Summary functions and maps |
| 3 | [Group-by: risk and leverage by sector](https://colab.research.google.com/github/assacohen1/fin6040-pandas-data/blob/main/notebooks/03_grouping_and_sorting.ipynb) | Grouping and sorting |
| 4 | [Data types, missing values and the P/E problem](https://colab.research.google.com/github/assacohen1/fin6040-pandas-data/blob/main/notebooks/04_data_types_and_missing_values.ipynb) | Data types and missing values |
| 5 | [Renaming and combining tables: growth, operating leverage, size](https://colab.research.google.com/github/assacohen1/fin6040-pandas-data/blob/main/notebooks/05_renaming_and_combining.ipynb) | Renaming and combining |

Run the cells from top to bottom and replace every `____` in the exercise cells with your own code.
The self-check cell below an exercise prints "Looks right!" when your answer is correct.
In Colab, use File > Save a copy in Drive to keep your work.

## Data

One row per US-listed company: fiscal-2025 financial statement items (Compustat) plus the 2025 stock
return, volatility and beta (CRSP). `companies_2025.csv` covers firms above $1B of market value,
`small_caps_2025.csv` the $300M-$1B firms, `fundamentals_2024.csv` last year's fundamentals with raw
Compustat names, and `gics_industries.csv` the GICS industry names. See `data_dictionary.md` for every column.

```python
import pandas as pd
DATA_URL = "https://raw.githubusercontent.com/assacohen1/fin6040-pandas-data/main/"
firms = pd.read_csv(DATA_URL + "companies_2025.csv")
```

Source: Wharton Research Data Services (Compustat North America, CRSP). For classroom use.
