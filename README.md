# Personal Finance Analysis

Analysis of 12 months of student spending and income (Oct 2025 – Sep 2026) using Python and pandas. The project covers data cleaning, summary analysis and visualisation, with a focus on how irregular income (termly student loan payments) shapes monthly cash flow.

> **Note:** The dataset is simulated. It was built to reflect realistic UK student spending patterns and does not contain any real personal financial data.

## Key findings

- **Food is half of all spending.** Groceries (31.6%) and eating out (19.3%) together make up about 51% of total spending. Eating out alone (£1,649) is more than shopping and transport combined.
- **Cash flow follows a "student loan cycle".** The three months with a Student Finance payment (Oct, Jan, Apr) each show a surplus of roughly £2,800. **The other 9 months all run at a deficit**, of between £39 and £412.
- **Summer work narrows the gap.** With more hours worked from June to September, monthly deficits fall to under £100 in three of those four months.
- **Overall:** £14,955 income vs £8,565 spending over the year.

![Spending by category](images/spending_by_category.png)

![Monthly income vs spending](images/income_vs_spending.png)

## Data cleaning

The raw data (543 transactions) contained several realistic quality issues:

| Issue | How it was handled |
|---|---|
| 8 duplicate rows | Removed |
| Inconsistent category labels (e.g. "food", "FOOD ", "Food") | Stripped whitespace and standardised capitalisation |
| 12 missing categories | Filled using the most common category for the same merchant |
| Amounts stored as text, some with "£" signs | Stripped symbols and converted to numbers |
| 4 missing amounts | Removed, as they couldn't be reliably estimated |
| Mixed date formats | Parsed to a single datetime format (UK day-first) |

The final clean dataset has 531 transactions.

## Tools

Python · pandas · matplotlib · Google Colab · Git/GitHub

## Repository structure
- `data/transactions_2025_26.csv`: raw (messy) dataset
- `images/`: charts used in this README
- `personal_finance_analysis.ipynb`: full analysis notebook

## How to run

Open `personal_finance_analysis.ipynb` in Google Colab or Jupyter. The notebook loads the data directly from this repository, so no setup is needed beyond pandas and matplotlib.

## Next steps

- Break spending down by day of the week and by merchant
- Build a simple monthly budget and compare actual spending against it
- Forecast end-of-term balance between loan payments
