S&P/Case-Shiller Home Price Index Analysis

Objective

This project aims to analyze publicly available data on economic, demographic, and real estate indicators to build a predictive model that explains the impact of these factors on the S&P/Case-Shiller Home Price Index, a key indicator of U.S. home prices, over the last two decades.

Introduction

The S&P CoreLogic Case-Shiller Home Price Indices track the price levels of single-family homes in the United States. The S&P CoreLogic Case-Shiller U.S. National Home Price Index provides a comprehensive view by aggregating data from nine regions and 20 major metropolitan areas, updated monthly. These indices measure percentage changes in housing market prices while maintaining a constant quality level, excluding variations due to house types, sizes, or physical characteristics.

Data and Methodology

Data Collection

Data for the analysis was sourced primarily from FRED. Key features include:





UNRATE: Unemployment Rate (Percent, Seasonally Adjusted, Monthly)



CSUSHPISA: S&P/Case-Shiller U.S. National Home Price Index (Index Jan 2000=100, Seasonally Adjusted, Monthly)



PERMIT: New Privately-Owned Housing Units Authorized (Thousands of Units, Seasonally Adjusted Annual Rate, Monthly)



PERMIT1: New Privately-Owned Housing Units Authorized: Single-Family Units (Thousands of Units, Seasonally Adjusted Annual Rate, Monthly)



MSACSR: Monthly Supply of New Houses (Months' Supply, Seasonally Adjusted, Monthly)



TTLCONS: Total Construction Spending (Millions of Dollars, Seasonally Adjusted Annual Rate, Monthly)



NASDAQCOM: NASDAQ Composite Index (Index Feb 5, 1971=100, Not Seasonally Adjusted, Daily, Close)



LFACTTTTUSM657S: Active Population Growth Rate (Seasonally Adjusted, Monthly)



HSN1F: New One Family Houses Sold (Thousands, Seasonally Adjusted Annual Rate, Monthly)



HOUST1F: New Privately-Owned Housing Units Started: Single-Family Units (Thousands of Units, Seasonally Adjusted Annual Rate, Monthly)



LFPR: Labor Force Participation Rate (PIB)



Housing Starts: New Housing Project (Towards Data Science)



INDPRO: Industrial Production: Cement (FRED)



Personal Income & Outlays: CSV (ALFRED)



New Privately-Owned Housing Units Completed: Total Units (FRED)

Data Preparation

When combining monthly and quarterly datasets, missing values are filled with the mode value to ensure completeness and consistency.

Exploratory Data Analysis

Exploratory Data Analysis (EDA) was conducted using ECDF (Empirical Cumulative Distribution Function) for effective histogram visualization and regression plotting to examine dataset variations.

Model Selection and Evaluation

Models evaluated include linear regression, random forest, and XGBoost. The random forest model performed best with an MSE of 8.33 and an adjusted R² of 0.99.

Results and Discussion

Exploratory Data Analysis

Key trends include a positive correlation between CSUSHPISA and HNFSEPUSSA, LFPR, TTLCONS, and CPI Adjusted Price. UNRATE shows an inverse correlation with employment.

Correlation Matrix





New Privately-Owned Housing Units Started: Single-Family Units (0.94 with CSUSHPISA)



Total Construction Spending (TTLCONS) (0.4 with CSUSHPISA)



Monthly Supply of New Houses (0.84 with CSUSHPISA)



New One Family Houses Sold (0.55 with CSUSHPISA)



NASDAQ Composite Index (0.26 with CSUSHPISA)

Machine Learning Models

Random forest was chosen for its balance of low MSE (8.33) and high R² (0.997), effectively identifying important parameters.

Conclusions

Key influencing factors on the S&P Home Price Index (HPI) include:





Personal Income & Outlays



Employment rate



Total Construction Spending (TTLCONS)



New privately owned housing



CPI-Adjusted Price



NASDAQ Composite Index (NASDAQCOM)



Monthly Supply of New Houses (MSACSR)

MECE Framework

The MECE (Mutually Exclusive, Collectively Exhaustive) framework categorizes factors influencing U.S. house prices into:





Economic Factor: Growth in the Economy, Unemployment, Customer Trust Rates, Offering, GDP, Home Sales Economy Mirror, Supply and Demand, Advance, Compliance, Competition, Extinct, Surplus Productivity



Location: Neighborhoods, Highways, Attractions, Schools, Area Desirability, Crime Rate



Government: Government laws, Property Taxes



Banks: Mortgage Availability, Interest Rates

Usage

To replicate this analysis, clone the repository and use the provided data sources. Scripts for data processing and modeling are included.

License

MIT License
