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

### 3. Build model
From above data, we choose to analyze:
- Region: California
- Type of avocado: organic

![image](https://user-images.githubusercontent.com/91864024/180389182-b0f634a5-4e11-4f43-bb29-bdc0c1267a78.png)


#### A. Avarage price prediction

Based on dataset, there are some models that can predict well the average price, such as: 
![image](https://user-images.githubusercontent.com/91864024/180379841-ef49c5e4-025f-407e-b665-1b38d6ab51f7.png)

==> Model ExtraTreesRegressor gives a higher score than RandomForest Regressor, RMSE and faster processing time than RandomForest and compared to other models ExtraTreesRegressor gives better results => choose ExtraTreesRegressor

**- Cross validation for ExtraTreesRegressor**

![image](https://user-images.githubusercontent.com/91864024/180380644-891906f4-d4fa-4883-b761-810b85216dc6.png)


==> we can choose `70% data for testing, 30% for training`

**- GridSearchCV for ExtraTreesRegressor**


![image](https://user-images.githubusercontent.com/91864024/180380716-f22e86e2-10a4-4a1d-a152-74e2b5325f35.png)

==>  we can choose `{'max_features': 'auto', 'n_estimators': 200, 'random_state': 1}`

**- Build model ExtraTreesRegressor**

![image](https://user-images.githubusercontent.com/91864024/180381717-9865d384-75f0-4eda-b187-145b7c0e9f8c.png)
![image](https://user-images.githubusercontent.com/91864024/180381770-d74e7978-043f-4221-a96c-03a614cdfe05.png)

**- Check result of model**

![image](https://user-images.githubusercontent.com/91864024/180381978-f990cd48-5dbb-48d9-97c2-f5cbd370b199.png)

==> Model ExtraTreesRegressor gives high score and mse, mae are all small => the selected model is suitable

#### B. Time-series prediction
**Predict average price with Facebook Prophet**
- Can we expand business for the next 5 years?
![image](https://user-images.githubusercontent.com/91864024/180386095-302c0abe-b266-477b-b55b-6d6c92a329c2.png)

==> we can see that the average price is inscreasing in the next 5 years --> it is possible to expand business.

**Predict average price with Arima**
- Can we expand business for the next 5 years?
![image](https://user-images.githubusercontent.com/91864024/180386258-6c76f26a-c2e3-4734-8296-92c5655734ef.png)

==> we can see that the average price is inscreasing in the next 5 years --> it is possible to expand business.

#### C. Conclusion
- Prophet test data: mae & mse ~ 10%, all data: mae & mse ~ 15% => acceptable small difference
- Arima test data: mae & mse ~ 20%, all data: mae & mse ~ 25% => big difference => do not choose this algorithm


==> Forecasting the growth trend from the next 12 months to the next 60 months of organic avocados in california, all 3 algorithms above have high growth rates and cyclical fluctuations => can expand production and business in this area

Thank you for your experience with my project. Hope you enjoy it!




