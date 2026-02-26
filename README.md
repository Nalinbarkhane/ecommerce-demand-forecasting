# E-Commerce Demand Forecasting & Inventory Optimization

Statistical analysis and machine learning for optimizing inventory decisions using 96,000+ e-commerce transactions

![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)
![Status](https://img.shields.io/badge/Status-Complete-success)

## Project Overview

End-to-end data science project analyzing Brazilian e-commerce transactions to develop demand forecasting models for inventory optimization. Achieved 92% prediction accuracy using machine learning.

### Key Results

- 92% prediction accuracy using Gradient Boosting
- 19% Q2 demand spike (statistically validated, p < 0.05)
- 15-20% inventory cost reduction potential
- 168 units safety stock for 95% service level
- Top 3 categories represent 26.7% of total demand

## Business Impact

**Problem:** Retailers lose $1.75 trillion annually from stockouts while 20-30% of capital is tied in overstock.

**Solution:** Data-driven forecasting framework using statistics and machine learning.

**Expected Savings:** $250,000 per year for a $10M revenue company.

## Methodology

### Statistical Analysis
- Descriptive statistics (mean, variance, coefficient of variation)
- Hypothesis testing (t-tests, ANOVA at significance level α = 0.05)
- Probability distributions and confidence intervals
- Linear and multiple regression

### Machine Learning
- Algorithms compared: Linear Regression, Random Forest, Gradient Boosting
- Best performing model: Gradient Boosting (R² = 0.92, MAE = 17.3)
- Validation approach: 70/30 train-test split

## Key Findings

1. **Category Concentration:** Top 3 categories account for 26.7% of total demand
2. **Seasonal Patterns:** Q2 shows peak demand (+18.9%, statistically significant)
3. **Demand Variability:** Coefficient of variation = 58%, indicating high uncertainty
4. **Prediction Accuracy:** 92% accuracy achieved with Gradient Boosting model

## Technologies Used

Python 3.11, pandas, numpy, scikit-learn, scipy, statsmodels, matplotlib, seaborn, Jupyter Notebook

## Dataset

**Source:** [Brazilian E-Commerce Public Dataset (Kaggle)](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)

**Size:** 100,000+ orders from September 2016 to August 2018

**Note:** Raw data files not included in repository. Download from Kaggle link above.

## Quick Start
```bash
# Install dependencies
pip install -r requirements.txt

# Launch Jupyter Notebook
jupyter notebook Ecommerce_Analysis.ipynb

# Run all cells to reproduce analysis
```

## Repository Contents

- `Ecommerce_Analysis.ipynb` - Main analysis notebook with complete workflow
- `requirements.txt` - Python package dependencies
- `model_comparison_complete.csv` - Model performance metrics
- `executive_dashboard_final.png` - Six-panel overview dashboard
- `fig_confidence_intervals.png` - Confidence interval visualization
- `fig_probability_distribution.png` - Distribution analysis
- `fig_probability_dashboard.png` - Probability analysis dashboard
- Additional visualization files

## Academic Context

This project was completed for **IE 6200: Engineering Probability and Statistics** at Northeastern University (Spring 2026, Prof. Rehab Ali).

**Course Requirements:** The foundational statistical analysis including descriptive statistics, hypothesis testing, ANOVA, probability distributions, and confidence intervals fulfills course requirements.

**Independent Extension:** Machine learning components (Random Forest, Gradient Boosting) represent independent exploration beyond course scope, demonstrating application of statistical foundations to modern predictive techniques.

## Skills Demonstrated

**Statistical Analysis:**
- Descriptive statistics and data summarization
- Hypothesis testing with proper significance levels
- ANOVA for multi-group comparison
- Probability distribution fitting and validation
- Confidence and prediction intervals
- Regression analysis and diagnostics

**Machine Learning:**
- Supervised learning for regression tasks
- Ensemble methods (Random Forest, Gradient Boosting)
- Model evaluation and comparison
- Feature engineering for temporal data

**Data Science:**
- Large-scale data processing (96,000+ records)
- Data cleaning and preparation
- Statistical visualization
- Business insight generation
- Technical communication

## Business Recommendations

Based on the analysis, the following strategies are recommended:

1. **Category Strategy:** Prioritize inventory for top 3 categories (bed_bath_table, health_beauty, sports_leisure)
2. **Seasonal Planning:** Build inventory 6-8 weeks before Q2 peak to handle 19% demand increase
3. **Safety Stock:** Maintain 168 units for 95% service level based on probability analysis
4. **Cost Optimization:** Expected 15-20% reduction in inventory holding costs
5. **Stockout Reduction:** Projected 20-30% decrease in stockout incidents

## Limitations

- Dataset from 2016-2018 may not reflect current post-pandemic e-commerce behavior
- Brazilian market data; generalizability to other markets requires validation
- Missing promotional and holiday indicator variables
- Aggregate daily-level analysis; product-level modeling could improve accuracy

## Future Work

- Incorporate promotional calendar and holiday indicators
- Add external economic variables
- Implement time series methods (ARIMA, Prophet)
- Develop category-specific forecasting models
- Validate findings with more recent datasets

## Author

**Nalin Barkhane**

Master of Science in Industrial Engineering  
Northeastern University  
Seeking co-op opportunities in Supply Chain Analytics, Operations Research, and Data Science

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- Prof. Rehab Ali - Course instruction for IE 6200
- Olist - Dataset provision via Kaggle
- Northeastern University - Academic support

---

**Last Updated:** February 2025

**Note:** This repository demonstrates both academic statistical rigor and practical data science skills. 
