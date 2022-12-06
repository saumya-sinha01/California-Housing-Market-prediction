# California-Housing-Market-prediction
In this project, we will be building machine learning models to predict how often a house is successfully sold out after it’s been listed and also predict the median sales price of the house.
We will be taking mortgage rate into account for the predictions.
Following an increase in mortgage rates, demand for buying a house decreases and inversely the amount being sold increases, which also leads to a drop in housing price. Our goal is to find out if this holds true.
Data Source:  Redfin/Kaggle, FRED Economic Data  .
California home prices data are taken from the Redfin data center by web scraping. Scrapping of data is done from redin website and filtered data only for California state. It includes California home prices in every county from 2012-2022
Mortgage data is taken from fred.stlouisfed.org. It contains the average 30-year fixed mortgage rate across the United States from 1970-2022. But we have used only from year 2012 - 2022

Expected Output: Quality Level (High=0, Medium=1, Low=2) and Median sales price

Steps for merging the datasets:
Converted  time series data to pandas.Timestamp in both the datasets
Extracted “Month’ and “Date” from Timestamp and made “Month” and “Date” columns in both datasets.
Since mortgage rate was  changing in a month so  took average and grouped them according to month and year
Combined both datasets using LEFT JOIN on “Month” and “Year”.

Models: 
Days on Market(Quality Taregt feature) :Logistic Regression, Random Forest(with and without regularisation), Decision Tree(with and without regularisation), Naive Bayes(Multinomial and Gaussian), KNN
Median Sale Price( Target feature): Random Forest, Linear Regression, Decision Tree
Evaluation: F1 Score, Accuracy, KFold cross validation, Precision, Recall
