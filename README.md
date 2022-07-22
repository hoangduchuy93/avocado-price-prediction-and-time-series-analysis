![image](https://user-images.githubusercontent.com/91864024/180345077-42161ab2-173a-4be8-8aa6-11ed334a2a6b.png)
# Avocado Price Prediction and Time-series Analysis
## I. Outline
- This project aims to make avocado price prediction and time-series analysis to predict growth of avocado in future.
- Analyze if we can expand our business to some regions of the US.
## II. Business Objective/ Problem
- Avocado “Hass”, a company based in Mexico, specializes in the production of a variety of avocados sold in the US. They have been very successful in recent years and want to expand. 
- They want to build a model to predict the average price of “Hass” avocados in the US in order to consider the expansion of existing avocado farms for avocado growing in other regions.
- This project is built on that request
## III. Project implementation
### 1. Business Understanding
Based on the above description (or after asking specific questions to the business and related subjects) => identify the problem:
- Currently: the company sells avocados in many parts of the United States with 2 types of avocados, regular and organic, packaged according to many standards (Small/Large/XLarge Bags), and 3 PLU (Product Look Up) is different (4046, 4225, 4770). But they don't have a model to predict avocado prices for the expansion.
- Objective/Problem: build a model to predict the average price of avocado "Hass" in the US => consider the expansion of production and business.

![image](https://user-images.githubusercontent.com/91864024/180348718-bacf9b86-220c-43da-9407-07dbe62b7394.png)
### 2. Data Understanding/ Acquire
- This data was downloaded from the Hass Avocado Board website in May of 2018 & compiled into a single CSV.
- You can refer to their website: https://hassavocadoboard.com/
- Data description: 
  - Date - The date of the observation
  - AveragePrice - the average price of a single avocado
  - type - conventional or organic
  - year - the year
  - Region - the city or region of the observation
  - Total Volume - Total number of avocados sold
  - 4046 - Total number of avocados with PLU 4046 sold
  - 4225 - Total number of avocados with PLU 4225 sold
  - 4770 - Total number of avocados with PLU 4770 sold

Can focus on solving two problems
- Problem 1: USA's Avocado AveragePrice Prediction – Using Regression algorithms like Linear Regression, Random Forest, XGB Regressor...
- Problem 2: Conventional/Organic Avocado Average Price Prediction for the future in California/NewYork… - using Time Series algorithms like ARIMA, Prophet...
