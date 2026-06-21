Multiple Linear Regression – Multi-Channel Marketing Analysis

A statistically rigorous analysis of how TV, Radio, and Social Media advertising spend drive Sales, built with `statsmodels` Ordinary Least Squares (OLS) regression. The project walks through multicollinearity diagnostics, model fitting, assumption validation, and translates the results into a business-ready budget recommendation.

## Project Goal

Determine which marketing channels meaningfully predict Sales, quantify their effect sizes, validate that the regression assumptions hold, and deliver a prioritized, evidence-based recommendation for allocating marketing budget across TV, Radio, and Social Media.

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- SciPy
- Statsmodels
- Jupyter Notebook

## Skills Demonstrated

- Exploratory Data Analysis (EDA)
- Missing Data Handling
- Correlation Analysis
- Multiple Linear Regression (OLS)
- Multicollinearity Assessment (VIF)
- Model Selection (Adjusted R², AIC, BIC)
- Residual Diagnostics
- Statistical Hypothesis Testing
- Business Interpretation of Statistical Results

### Dataset Summary

| Property | Value |
|----------|------|
| Observations | 4,572 |
| Predictors | 3 |
| Target Variable | Sales |
| Numeric Variables | 4 |
| Missing Data | <1% per variable |

| Column | Description | Units |
|---|---|---|
| `TV` | TV advertising spend | $1,000s |
| `Radio` | Radio advertising spend | $1,000s |
| `Social_Media` | Social media advertising spend | $1,000s |
| `Sales` | Resulting sales | $1,000s |

- Each column has a small amount of missing data (well under 1% per column), handled via row-wise deletion after confirming the missingness appears random and unconcentrated (see notebook Section 2 for the full justification).
- File: [`marketing_data.csv`](./marketing_data.csv)

## Analysis Workflow

The notebook ([`multiple_regression_analysis.ipynb`](./multiple_regression_analysis.ipynb)) follows this structure:

Data Loading

        ↓
        
Data Cleaning

        ↓
        
Exploratory Data Analysis

        ↓
        
Correlation Analysis

        ↓
        
Multicollinearity Assessment

        ↓
        
OLS Model Fitting

        ↓
        
Model Evaluation

        ↓
        
Model Refinement

        ↓
        
Residual Diagnostics

        ↓
        
Coefficient Interpretation

        ↓
        
Business Recommendation

## Exploratory Data Analysis

images/distributions.png

## Correlation Analysis

images/correlation_heatmap.png

## Pairwise Relationships

images/pairplot.png

## Regression Model
The fitted Ordinary Least Squares model follows

Sales = β₀ + β₁(TV) + β₂(Radio) + β₃(Social_Media) + ε

where

- β₀ = intercept
- β₁–β₃ = regression coefficients
- ε = random error

## Key Findings (Summary)

| Finding | Result |
|---------|--------|
| Best Predictor | TV Advertising |
| TV Significance | p < 0.001 |
| Radio Significance | Not Significant |
| Social Media Significance | Not Significant |
| Multicollinearity | None (VIF < 5) |
| OLS Assumptions | No substantial violations detected |
| Recommended Model | TV-only model |

## Notes on Methodology

- Missing values were dropped row-wise (≈0.6% of rows) rather than imputed, since the assignment scope calls for a straightforward, defensible cleaning approach and the missingness rate was low enough that imputation would add complexity without materially changing the conclusions.
- Model selection between the full three-predictor model and the reduced TV-only model was based on **Adjusted R², AIC, and BIC** — all of which favored the simpler model, consistent with the non-significant p-values for Radio and Social Media.
- This is an educational dataset; the unusually high TV–Sales correlation (0.999) is part of what makes it effective for illustrating predictor significance and multicollinearity concepts clearly. Real-world marketing data is typically noisier and may show diminishing returns or interaction effects not captured by this linear, additive model — see the notebook's caveats section for next-step suggestions (e.g., A/B testing, interaction terms).

## Model Performance

📷 Actual vs Predicted Plot

images/predicted_vs_actual.png

## Residual Diagnostics

Diagnostic analyses found no substantial evidence of violations of the core OLS assumptions.

### Residual vs Fitted

📷 images/residual_plot.png

### Normal Q-Q Plot

📷 images/qq_plot.png

### Scale-Location Plot

📷 images/scale_location.png

### Residual Histogram

📷 images/residual_histogram.png

## Limitations

- The analysis assumes a linear relationship between advertising spend and sales.
- Interaction effects between marketing channels were not modelled.
- External factors such as seasonality, pricing, and competitor activity were not included.

## Future Improvements

Possible extensions include

- Ridge Regression
- LASSO Regression
- Elastic Net
- Polynomial Regression
- Interaction Terms
- Cross-Validation
- Random Forest Regression
- Gradient Boosting Regression

## Environment Setup

### Requirements
- Python 3.9+
- Jupyter Notebook or JupyterLab

## Repository Contents

```
.
├── multiple_regression_analysis.ipynb   # Full analysis notebook with executed outputs
├── marketing_data.csv                   # Raw dataset
└── README.md                            # This file
```

## Author

**Musa Abdulmalik**

Medical Professional | Data Science Enthusiast  
Interested in Healthcare Analytics, Machine Learning, and Statistical Modeling

Interested in

- Healthcare Analytics
- Machine Learning
- Statistical Modelling
- Medical Research
