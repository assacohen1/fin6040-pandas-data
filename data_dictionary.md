# Data dictionary

Source: WRDS - Compustat North America (fundamentals, fiscal year 2025) and CRSP 2.0 daily stock file (calendar 2025). Built by `download_wrds_data.py` on 2026-09-17.

Universe: companies listed on NYSE, NYSE American or NASDAQ, reporting in USD, ordinary common shares per CRSP, at least 200 daily returns in 2025, market cap above $1,000 million at fiscal year end (`companies_2025.csv`) or between $300 million and $1,000 million (`small_caps_2025.csv`). Rows are sorted by market cap, largest first.

## companies_2025.csv (2,067 rows)

| column | description |
|---|---|
| `ticker` | Stock ticker symbol (unique; use as the row label) |
| `company` | Company name |
| `sector` | GICS sector (11 values) |
| `industry_code` | GICS industry code (6 digits); names in gics_industries.csv |
| `exchange` | Primary listing exchange (NYSE, NYSE American, NASDAQ) |
| `state` | State of headquarters (missing for some foreign-headquartered firms) |
| `ipo_date` | First trading date in Compustat (YYYY-MM-DD); missing for old listings |
| `fiscal_year_end` | Last day of fiscal year 2025 (YYYY-MM-DD) |
| `employees` | Employees, thousands |
| `sales` | Revenue (Compustat SALE, REVT when SALE is missing), $ millions |
| `cogs` | Cost of goods sold (COGS), $ millions; not reported by most financials |
| `sga` | Selling, general & administrative expense (XSGA), $ millions |
| `r_and_d` | Research & development expense (XRD), $ millions; missing when not reported |
| `ebitda` | Earnings before interest, taxes, depreciation & amortization (EBITDA), $ millions |
| `ebit` | Operating income after depreciation (OIADP), $ millions |
| `interest_expense` | Interest expense (XINT), $ millions |
| `net_income` | Net income (NI), $ millions |
| `dividends` | Common dividends (DVC), $ millions; missing usually means none |
| `capex` | Capital expenditures (CAPX), $ millions |
| `cfo` | Cash flow from operations (OANCF), $ millions |
| `total_assets` | Total assets (AT), $ millions |
| `total_liabilities` | Total liabilities (LT), $ millions |
| `total_debt` | Long-term debt (DLTT) + debt in current liabilities (DLC), $ millions |
| `cash` | Cash and short-term investments (CHE), $ millions |
| `book_equity` | Common equity (CEQ), $ millions |
| `shares_out` | Common shares outstanding (CSHO), millions |
| `price` | Share price at fiscal year end (PRCC_F), $ |
| `market_cap` | price x shares_out, $ millions |
| `ret_2025` | Total stock return over calendar 2025 (CRSP daily returns compounded), decimal |
| `vol_2025` | Annualized volatility: standard deviation of 2025 daily returns x sqrt(252), decimal |
| `beta_2025` | Slope of daily returns on SPY daily returns in 2025 |

## small_caps_2025.csv

Same columns as `companies_2025.csv` except `market_cap` is called `mktcap` and `vol_2025` is called `vol` (on purpose: notebook 5 practices renaming before combining).

## fundamentals_2024.csv

Fiscal year 2024 for the same companies, with raw Compustat names: `gvkey`, `tic` (ticker), `conm` (company name), `fyear`, `sale` (sales), `cogs`, `xsga` (SG&A), `oiadp` (EBIT), `ni` (net income), `at` (total assets). Companies that were not public in that year are absent.

## gics_industries.csv

`industry_code`, `industry_name`: one row per GICS industry appearing in the data.
