# Retail Sales Forecasting with Machine Learning

## Project Overview

This project uses historical retail sales data to explore sales forecasting with Python and machine learning. It compares a baseline approach with Random Forest models and evaluates how historical sales patterns, calendar features, holidays, and promotions relate to forecasting performance.

## Objectives

- Analyze historical retail sales trends.
- Engineer calendar, lag, and rolling-average features.
- Train and compare multiple forecasting approaches.
- Evaluate model performance using MAE and RMSE.
- Investigate the contribution of holiday and promotion-related features.

## Tools and Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Jupyter Notebook

## Models Evaluated

1. Baseline Model
2. Random Forest Regressor
3. Random Forest with Holiday Features
4. Promotion-Only Random Forest

## Results

| Model | MAE | RMSE |
|---|---:|---:|
| Baseline | 267,597.91 | 321,869.46 |
| Random Forest | 77,640.95 | 122,620.00 |
| Random Forest + Holiday Features | 77,083.00 | 122,154.26 |
| Promotion-Only Random Forest | 147,353.94 | 189,959.77 |

The Random Forest model with holiday features achieved the lowest validation errors among the evaluated models.

- **Best MAE:** 77,083.00
- **Best RMSE:** 122,154.26
- **MAE reduction compared with baseline:** Approximately 71.2%

These metrics represent validation error, not forecasting accuracy.

## Feature Engineering

The models use features such as:

- Day of the week
- Month
- Day of the month
- Previous-day sales (`lag_1`)
- Sales from 7 and 14 days earlier (`lag_7`, `lag_14`)
- Previous 7-day rolling average
- Holiday-related indicators in the holiday-enhanced model

Lag and rolling features are calculated using historical sales, excluding the current day's target.

## Validation Strategy

The data was split chronologically to preserve the order of time.

- **Training period:** January 15, 2013 – September 11, 2016
- **Validation period:** September 12, 2016 – August 15, 2017
- **Training observations:** 1,333
- **Validation observations:** 337

The evaluation represents one-step-ahead predictions where actual sales from previous days are available when generating each prediction. It does not directly measure performance when forecasting the entire future period in advance.

## Key Learnings

- Historical sales patterns can be valuable forecasting features.
- Time-based validation is important for time-series problems.
- Holiday features produced a small improvement over the standard Random Forest model.
- Promotion-only features performed less effectively than the full feature set.
- MAE and RMSE provide complementary ways to assess prediction errors.

## Limitations and Future Improvements

- Evaluate recursive forecasting for multi-day forecasts without access to future actual sales.
- Analyze performance across individual stores and product categories.
- Explore additional time-series features and hyperparameter tuning.
- Test the model across multiple chronological validation periods.

## Conclusion

This project demonstrates a complete introductory machine learning workflow for retail sales forecasting, from feature engineering and chronological validation to model comparison and error analysis.

The best evaluated model was Random Forest with holiday features, achieving an MAE of 77,083.00 and an RMSE of 122,154.26 on the validation period.

*Note: Validation results do not guarantee equivalent performance on unseen future data.*

## Author

**Shumaila Yaseen**

BS Computer Science Student | Aspiring Data Scientist


