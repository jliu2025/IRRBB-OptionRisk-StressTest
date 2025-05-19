# IRRBB-OptionRisk-StressTest

## Overview

This project models **Interest Rate Risk in the Banking Book (IRRBB)** with a specific focus on **option risk**, capturing behavioral elements such as **loan prepayments** and **non-maturity deposit (NMD) withdrawals**. By applying parallel rate shocks ranging from -200 to +200 basis points, the analysis measures the impact on:

- 🔺 ΔNII (Change in 12-month Net Interest Income)
- 🔺 ΔEVE (Change in Economic Value of Equity)
-  Net Cash Position (Liquidity impact after 1 year)

The results are visualized using an interactive **Power BI** dashboard.

---

## Project Structure

```text
IRRBB-OptionRisk-StressTest/
│
├── Gen_balance_sheet.ipynb           # (To be created) Generate synthetic balance sheet data
├── StressTesting.ipynb               # Core stress testing logic with behavior models
├── Balance_sheet.csv                 # Input: loan and deposit portfolio
├── Stress_Test_Output.csv            # Output: simulation results by scenario
├── StressTesting_Report.pbix         # Power BI dashboard visualizing results
├── README.md                         # Project documentation
```

## Methodology

Behavioral Assumptions:
Loan Prepayment (prepayment_rate)
Modeled as Conditional Prepayment Rate (CPR)

Based on loan type, rate differential, and sensitivity

Maximum CPR capped at 30%

NMD Withdrawal (nmd_decay_rate)
Differentiates between core and non-core balances

Behavior based on deposit type, rate gap, and sensitivity

Weighted average decay rate applied per product

Stress Testing:
Interest rate shock range: -200 to +200 bps in 25 bps increments

Assumes base market rate of 4.5%
Simulates:

Year 1 interest flows (ΔNII)

Lifetime present value of flows (ΔEVE)

Net cash position after Year 1 (liquidity impact)


## Dashboard Highlights (Power BI)
Balance Sheet Summary

Deposit and loan portfolio distribution

Weighted rates and maturities

Shock Impact Summary

ΔNII and ΔEVE under +200 and -200 bps scenarios

Gap profile showing loan/deposit mismatch over maturity buckets

Scenario Drilldown

Compare base vs. stressed scenario inputs (e.g., prepay, decay)

Track principal, interest, and cash movement over Year 1

Trend Visualization

ΔNII, ΔEVE, and Net Cash Position across all shock levels

Tabular output by component (loan/deposit behavior)

## How to Run
Prepare balance sheet
Modify Balance_sheet.csv with your portfolio data

Run simulation
Open and execute StressTesting.ipynb
Generates Stress_Test_Output.csv

Visualize in Power BI
Open StressTesting_Report.pbix
Load the CSV output and explore interactive charts

## License
This project is intended for educational and exploratory use. For production use, proper model validation, regulatory compliance, and audit controls are required.

## Author
### Jonathan Liu
LinkedIn: linkedin.com/in/jonathan-liu-ca

