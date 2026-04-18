# E-Commerce Demand Forecasting: Statistical Analysis for Inventory Optimization

**Course:** IE 6200 — Engineering Probability and Statistics  
**Institution:** Northeastern University, Mechanical and Industrial Engineering Department  
**Section:** Sec 1 — Spring 2026  
**Instructor:** Prof. Rehab Ali  
**Team:** Group 3

---

## Project Overview

This project applies probability and inferential statistics to a real-world Brazilian e-commerce dataset to uncover demand patterns and support data-driven inventory planning decisions. Using over 107,000 cleaned orders spanning 2016–2018, seven distinct statistical methods are applied to answer key operational questions around staffing, stock levels, and category management.

---

## Dataset

**Source:** [Olist Brazilian E-Commerce Public Dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) — Kaggle, 2018.

| File | Description | Records |
|---|---|---|
| `olist_orders_dataset.csv` | Order timestamps and delivery status | 99,441 |
| `olist_order_items_dataset.csv` | Line items with product IDs and prices | 112,650 |
| `olist_products_dataset.csv` | Unique products with category codes | 32,951 |
| `product_category_name_translation.csv` | Portuguese-to-English category names | 71 categories |

All data files must be placed in the `data/` folder before running the notebook.

---

## Project Structure

```
IE6200_Project/
│
├── data/                               # Raw CSV data files (required)
│   ├── olist_orders_dataset.csv
│   ├── olist_order_items_dataset.csv
│   ├── olist_products_dataset.csv
│   └── product_category_name_translation.csv
│
├── Ecommerce_Analysis.ipynb            # Main analysis notebook
├── Group3_Final_Report.docx            # Final written report
├── Group3_Presentation.pptx           # Presentation slides
│
├── figures/                            # All generated figures (auto-created on run)
│   ├── fig_chi_square_day_of_week.png  # Chi-square test: orders by day of week
│   ├── fig_probability_distribution.png# KS test histogram & Q-Q plot
│   ├── fig_confidence_intervals.png    # CI and prediction interval comparison
│   ├── fig_correlation_heatmap.png     # Pearson correlation matrix heatmap
│   ├── fig_scatterplot_price_demand.png# Price vs daily demand scatterplot
│   ├── fig_boxplot_category_demand.png # Demand by top-5 product categories
│   ├── fig_probability_dashboard.png   # 4-panel probability analysis dashboard
│   └── fig_business_implications.png   # Business implications summary
│
├── hypothesis_test_results.csv        # Exported hypothesis test results
├── category_statistics_complete.csv   # Category-level statistics
├── model_comparison_complete.csv      # Model comparison output
│
└── README.md                          # This file
```

---

## Requirements

### Python Version
Python 3.9 or higher

### Required Libraries
```
pandas
numpy
matplotlib
seaborn
scipy
```

Install all dependencies with:
```bash
pip install pandas numpy matplotlib seaborn scipy
```

---

## How to Run

### Step 1 — Clone or download the project
Make sure all files are in the same folder structure shown above, with the `data/` folder containing all four CSV files.

### Step 2 — Install dependencies
```bash
pip install pandas numpy matplotlib seaborn scipy
```

### Step 3 — Open the notebook
Open `Ecommerce_Analysis.ipynb` in one of the following:
- **VS Code** — open the file directly from the Explorer panel
- **Jupyter Notebook** — run `jupyter notebook` in the terminal
- **JupyterLab** — run `jupyter lab` in the terminal

### Step 4 — Run all cells
- **VS Code:** Click **"Run All"** in the notebook toolbar (top of the notebook)
- **Jupyter Notebook:** Kernel → Restart & Run All
- **JupyterLab:** Kernel → Restart Kernel and Run All Cells

> **Important:** Always run from Cell 0. Every cell depends on the `data` variable created in Cell 1. Running cells out of order will cause `NameError`.

---

## Notebook Structure

| Cell | Section | Description |
|---|---|---|
| 0 | Setup | Import libraries, load raw CSV files |
| 1 | Data Cleaning | Merge datasets, filter delivered orders, remove outliers |
| 2 | Cleaning Assessment | Quantify impact of each cleaning step |
| 3 | Descriptive Statistics | Summary stats: orders, revenue, categories |
| 4 | Time Series Analysis | Monthly demand trend plot |
| 5 | Category Distribution | Price distribution by top-10 categories |
| 6 | *(Legacy t-test)* | Basic weekday/weekend t-test (early version) |
| 7 | Executive Dashboard | Multi-panel demand overview figure |
| 8 | Pie Charts | Market share by category |
| 9 | **Hypothesis Testing** | 4 tests with all 7 steps (t-test, ANOVA ×2, Chi-Square) |
| 10 | Assumptions Verification | Levene's test, Shapiro-Wilk normality check |
| 11 | **KS Distribution Fitting** | Kolmogorov-Smirnov normality test with all 7 steps |
| 12 | Probability Calculations | Normal distribution P(X > x) calculations |
| 13 | **Confidence Intervals** | 90%, 95%, 99% CIs and prediction intervals |
| 14 | Business Implications | Operational recommendations from findings |
| 15 | Probability Dashboard | 4-panel probability analysis chart |
| 16 | Correlation Analysis | Pearson correlation matrix and heatmap |
| 17 | Scatterplot | Price vs demand with trend line |
| 18 | Boxplot | Demand distribution by top-5 categories |
| 19 | Results & Conclusions | Summary table of all 8 tests, key findings |
| 20 | Strengths & Weaknesses | Analysis limitations and strengths |
| 21 | Next Steps | Short-term and long-term future work |
| 22 | References | Final conclusions and IEEE bibliography |

---

## Statistical Methods Applied

All 7 methods follow the professor-required 7-step format:  
*(1) Parameter of interest → (2) H₀ → (3) H₁ → (4) Formula → (5) Compute → (6) P-value → (7) Decision*

| # | Method | Question | Result |
|---|---|---|---|
| 1 | **Welch's t-test** | Is weekday demand different from weekend demand? | REJECT H₀ — p < 0.001 |
| 2 | **One-Way ANOVA** | Does demand vary significantly across quarters? | Fail to reject H₀ — p = 0.066 |
| 3 | **One-Way ANOVA** | Does demand differ across top-5 product categories? | REJECT H₀ — p < 0.001 |
| 4 | **Chi-Square GoF** | Are orders uniformly distributed across days of the week? | REJECT H₀ — p < 0.001 |
| 5 | **KS Distribution Fit** | Does daily demand follow a Normal distribution? | REJECT H₀ — p = 0.004 |
| 6 | **Pearson Correlation** | Is price correlated with demand? | Fail to reject H₀ — p = 0.056 |
| 7 | **Confidence Intervals** | What is the 95% CI for mean daily demand? | CI = [171, 180] orders/day |

---

## Key Results

| Finding | Value | Practical Action |
|---|---|---|
| Weekday mean demand | 189.9 orders/day | Staff 35% more on weekdays |
| Weekend mean demand | 140.2 orders/day | Reduce weekend capacity |
| 90th percentile stock target | 306 units/day | Recommended daily baseline |
| 95th percentile stock target | 343 units/day | Promotional event buffer |
| 99th percentile stock target | 413 units/day | Extreme peak coverage |
| Price-demand correlation | r = −0.077 | Price is not a demand driver |
| Quarterly seasonality | p = 0.066 | Uniform year-round policy is appropriate |
| Day-of-week distribution | χ² >> 12.59 | Day-specific schedules are justified |

---

## Output Files Generated

Running the notebook produces the following figures:

All figures are saved to the `figures/` folder automatically when the notebook runs.

| File | Description |
|---|---|
| `figures/fig_chi_square_day_of_week.png` | Observed vs expected orders by day of week |
| `figures/fig_probability_distribution.png` | Demand histogram with normal fit + Q-Q plot |
| `figures/fig_confidence_intervals.png` | CI and prediction interval comparison |
| `figures/fig_correlation_heatmap.png` | Pearson correlation matrix heatmap |
| `figures/fig_scatterplot_price_demand.png` | Average daily price vs daily demand |
| `figures/fig_boxplot_category_demand.png` | Demand distribution by top-5 categories |
| `figures/fig_probability_dashboard.png` | 4-panel probability analysis dashboard |
| `figures/fig_business_implications.png` | Business implications summary |

---

## References

- [1] D. C. Montgomery and G. C. Runger, *Applied Statistics and Probability for Engineers*, 7th ed. Hoboken, NJ: Wiley, 2018.
- [2] R. E. Walpole, R. H. Myers, S. L. Myers, and K. Ye, *Probability and Statistics for Engineers and Scientists*, 9th ed. Upper Saddle River, NJ: Pearson, 2012.
- [3] A. Agresti and B. Finlay, *Statistical Methods for the Social Sciences*, 4th ed. Upper Saddle River, NJ: Pearson, 2009.
- [4] Olist, "Brazilian E-Commerce Public Dataset by Olist," Kaggle, 2018. [Online]. Available: https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce
- [5] P. Virtanen et al., "SciPy 1.0: Fundamental Algorithms for Scientific Computing in Python," *Nature Methods*, vol. 17, pp. 261–272, 2020.
