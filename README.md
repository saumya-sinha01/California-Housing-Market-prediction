# Predicting House Sales Success and Median Sales Price

This project focuses on building machine learning models to predict two key outcomes in the real estate market: the likelihood of a house being successfully sold after listing, and the median sales price of the property. We specifically account for mortgage rates in our predictions, as higher mortgage rates typically reduce the demand for purchasing homes, which paradoxically can increase the number of homes sold and lead to a decline in housing prices. Our objective is to verify whether this relationship holds true.

## Data Sources

- **Housing Data**: California home prices were obtained from Redfin through web scraping. The dataset covers home prices in every county across California from 2012 to 2022.
- **Mortgage Data**: Mortgage rate data was sourced from the FRED Economic Data (fred.stlouisfed.org), providing the average 30-year fixed mortgage rates in the United States from 1970 to 2022. For this analysis, we focused on data from 2012 to 2022.

## Expected Outcomes

- **Quality Level of Sales**: Classified as High (0), Medium (1), Low (2)
- **Median Sales Price**

## Data Merging Process

1. Converted time series data in both datasets to `pandas.Timestamp`.
2. Extracted “Month” and “Year” from the timestamp and created corresponding columns in each dataset.
3. Since mortgage rates vary within a month, we calculated the monthly average and grouped the data by month and year.
4. Merged both datasets using a LEFT JOIN based on “Month” and “Year”.

## Models Employed

### For Days on Market (Quality Target Feature):

- Multinomial Logistic Regression
- Random Forest (with and without regularization)
- Decision Tree (with and without regularization)
- Naive Bayes (Multinomial and Gaussian)
- K-Nearest Neighbors (KNN)

### For Median Sale Price (Target Feature):

- Random Forest
- Linear Regression
- Decision Tree

## Evaluation Metrics

- F1 Score
- Accuracy
- K-Fold Cross Validation
- Precision
- Recall
