**Name:** Anthony Logie  
**Company:** Caterpillar Inc.  
**Date:** 4/24/2026

---

## 1. Problem Statement

This model evaluates the financial performance of Caterpillar Inc. over a two-year period, using the most recent fiscal year and the prior year, and is structured using standard accounting and ratio statements. 
The main objective is to assess Profitability, Efficiency, Liquidity, Leverage, and Value creation. 
The model integrates financial statement data with inputs to produce useful insights for financial management and analysis.

---

## 2. Inputs (Known Variables)

### Balance Sheet Inputs (Current & Prior Year)

| Variable | Description |
|----------|------------|
| Cash and Cash Equivalents | Liquid assets available |
| Short-Term Investments | Marketable securities |
| Accounts Receivable (Net) | Net credit sales outstanding |
| Inventory | Goods held for sale |
| Total Current Assets | Sum of current assets |
| Property, Plant & Equipment (Net) | Long-term operating assets |
| Total Assets | Total company resources |
| Accounts Payable | Short-term obligations |
| Short-Term Debt | Current portion of debt |
| Total Current Liabilities | Short-term obligations |
| Long-Term Debt | Non-current debt |
| Total Liabilities | Total obligations |
| Shareholders’ Equity | Residual ownership |

---

### Income Statement Inputs

| Variable | Description |
|----------|------------|
| Revenue (Net Sales) | Total sales |
| Cost of Goods Sold | Cost of production |
| Gross Profit | Revenue - COGS |
| Operating Income (EBIT) | Earnings before interest & taxes |
| Interest Expense | Cost of debt |
| Income Before Tax | Pre-tax earnings |
| Income Tax Expense | Taxes paid |
| Net Income | Final profit |

---

### Cash Flow Statement Inputs

| Variable | Description |
|----------|------------|
| Operating Cash Flow | Cash from operations |
| Capital Expenditures | Investment in assets |
| Depreciation & Amortization | Non-cash expense |

---

### Market / Analyst Inputs

| Variable | Description |
|----------|------------|
| Share Price | Market value per share |
| Shares Outstanding | Total shares |
| Market Capitalization | Price × Shares |
| Cost of Capital (WACC) | Required return |
| Tax Rate | Assumed 21% |

---

## 3. Named Range Conventions

All inputs follow this structure:

`[STATEMENT]_[variable]_[year]`

### Examples
- `BAL_total_assets_2024`
- `BAL_total_assets_2023`
- `INC_net_income_2024`
- `INC_revenue_2024`
- `CASH_operating_2024`
- `MKT_share_price`
- `ASSUM_tax_rate`
- `ASSUM_wacc`

### Derived Ranges
- `AVG_total_assets = (BAL_total_assets_2024 + BAL_total_assets_2023) / 2`
- `AVG_equity = (BAL_equity_2024 + BAL_equity_2023) / 2`
- `NOPAT = INC_operating_income_2024 * (1 - ASSUM_tax_rate)`

---

## 4. Assumptions & Constraints

- Tax rate assumed at 21%
- Annual data
- No off-balance-sheet items included
- Market inputs treated as constant
- Averages used for assets and equity
- Interest treated on a simple annual basis

---

## 5. Calculation Flow

### A. Derived Inputs
- Average Assets = `(current + prior) / 2`
- Average Equity = `(current + prior) / 2`
- NOPAT = `EBIT × (1 - tax rate)`
- Invested Capital ≈ `Total Assets - Current Liabilities`

---

### B. Performance Ratios
- MVA = `Market Cap - Book Equity`
- Market-to-Book = `Market Cap / Equity`
- EVA = `NOPAT - (Invested Capital × WACC)`

---

### C. Profitability Ratios
- ROA = `Net Income / AVG_total_assets`
- ROE = `Net Income / AVG_equity`
- ROC = `NOPAT / Invested Capital`

---

### D. Efficiency Ratios
- Asset Turnover = `Revenue / AVG_total_assets`
- Inventory Turnover = `COGS / AVG_inventory`
- Days Inventory = `365 / Inventory Turnover`
- A/R Turnover = `Revenue / AVG_accounts_receivable`
- Collection Period = `365 / A/R Turnover`

---

### E. Leverage Ratios
- Debt-to-Assets = `Total Liabilities / Total Assets`
- Debt-to-Equity = `Total Liabilities / Equity`
- Interest Coverage = `EBIT / Interest Expense`
- Debt Burden = `Net Income / EBIT`

---

### F. Liquidity Ratios
- Current Ratio = `Current Assets / Current Liabilities`
- Quick Ratio = `(Cash + Receivables) / Current Liabilities`
- Cash Ratio = `Cash / Current Liabilities`
- NWC-to-Assets = `(CA - CL) / Total Assets`

---

### G. Du Pont Decomposition

- Profit Margin = `Net Income / Revenue`
- Asset Turnover = `Revenue / Assets`
- Equity Multiplier = `Assets / Equity`

**ROE = Profit Margin × Asset Turnover × Equity Multiplier**

---

## 6. Outputs

The model produces:

- Ratio summary table by category
- Year-over-year comparison
- KPI dashboard (profitability, liquidity, leverage)
- Du Pont breakdown
- Value creation metrics (EVA, MVA)

---

## 7. Model Review — What Worked & What to Improve

### What Worked
- Accurate ratio calculations across all categories
- Logical organization of financial metrics
- Use of averages improved accuracy
- Du Pont model correctly implemented

---

### What to Improve
- Inconsistent naming conventions in some areas
- Some formulas are hardcoded instead of being dynamic
- Limited error handling
- Layout could be more modular

---

### Enhancements
- Fully standardized named ranges
- Add error checks
- Separate sheets: Inputs / Calculations / Outputs
- Add scenario analysis
- Expand to multi-year trend analysis

---

## 8. Limitations & Next Steps

### Limitations
- Only two-year analysis
- No industry benchmarking
- Simplified WACC assumption
- No forecasting

---

### Next Steps
- Add multi-year trend analysis
- Include peer comparison
- Build an AI-driven analysis prompt
- Add forecasting and scenario modeling
