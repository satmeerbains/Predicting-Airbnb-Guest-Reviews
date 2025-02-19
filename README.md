# Predicting Airbnb Guest Reviews Using Machine Learning Modeling

## 1. Abstract
This exercise proposes the use of predictive machine learning modeling to estimate the guest reviews at Airbnb stays based on various features. The data is a random sample of a dataframe gathered from stays in the city of London, England on November 5th, 2019. The model contains various features representing the host(s), rules, location, etc. and other information of the stay itself. Using machine learning techniques, we develop a model to predict guest reviews with a reasonable level of accuracy. Our findings suggest that certain factors, such as price, location, and host response time, have a significant impact on the reviews given by guests. The results of this study can be valuable for both hosts looking to optimize their listings and platforms like Airbnb seeking to improve guest satisfaction. Findings suggest that certain factors, such as number of previous reviews, price, location, availability, etc. have a significant impact on the reviews given by guests. 

## 2. Introduction
Airbnb is an online marketplace where customers can book homestays and experiences in various countries. Each time a guest stays at an accommodation they are encouraged to leave a review and a score on the experience. A review is a key performance indicator of how successful a host/stay is. It helps future guests make informed decisions and provides feedback to hosts about their service quality. Predicting guest reviews before a booking can help to better inform hosts on the aspects that lead to customer satisfaction. This paper explores the use of machine learning techniques to predict the reviews that guests would give to Airbnb listings, based on historical data from November 5th, 2019. The goal is to develop a model that accurately predicts these reviews and offers insights into the factors that most influence guest satisfaction.

## 3. Data Description
The data contains 106 columns and 39.9 million rows; however, a random sample was taken due to computational dependencies. 

The data was gathered from stays in the city of London, England on November 5th, 2019. The source of this data was collected and prepared by Inside Airbnb project (http://insideairbnb.com/).

## 4. Methodology

### 4.1 Data Exploration

Data and necessary libraries were imported. A custom function was created to show the missing data, number of unique values, and the data type for each feature in our data frame.

### 4.2 Data Exploration

#### Formatting features
* Converted features with a $ and % sign to numeric.
* Converted date features.
* Transformed binary features to Boolean for future use.
* In preparation for dummy variables, categorical values that have disproportionate value counts were removed.

#### Data Cleaning
##### Missing data
* Removed features that have more than 75% missing data since imputation will not help it be of any significance in our model.
* Imputation was performed for the rest of the features with missing data.

#### Dummy Variables
Dummy variables were created and concatenated to the numeric columns of the data frame.

### 4.3 Feature Selection
#### Finding collinearity and removing redundancies within features.
#### Determining multicollinearity Check with Variance Inflation Factor (VIF).
#### Calculating Gini's Importance.
#### Principal Component Analysis.
#### Scaling Data.

### 4.4 Building the Machine Learning Model
Built a model of various algorithms that
* Fit the model.
* Calculated and printed the evaluation metrics.
* Produced train and test error, with the trained model name with y_predict to then calculate these metrics for all of the models at once.

Regression models Ridge, Decision Tree, Random Forest, XGBoost, LGBM, and MLP were used.

Scalers Standard, MinMax, and no scale were used

Different sets of features were created: full dataset, 40, 20, and 10 where the selection was made according to Gini's index.

### 4.5 Results
To compare predictions with original values and calculate them. Three for loops were used inside each other taking values from the dictionaries created, then calculating the RMSE for each of our models.

The best performing model was Ridge	regression with 40 selected features (using Gini's Importance) with a scaling method of MinMax. It had a RMSE of 6.697556.

### 4.6 Conclusion
This study demonstrates the potential of machine learning to predict Airbnb guest reviews with a relatively high degree of accuracy. The findings highlight the importance of factors such as number of previous reviews, number of rooms available, cleaning fee, price, location, availability in determining guest satisfaction. By leveraging predictive models, both hosts and platform managers can gain valuable insights into the factors driving guest reviews, helping them improve their offerings and enhance user experiences.

Future research could extend this work by incorporating the text-based data such as description of the stay, summary etc. using natural language processing to gain insight on top phrases/words used in negative or positive reviews. Exploring more advanced machine learning techniques like deep learning models should also be considered
![image](https://github.com/user-attachments/assets/d6a3c3e5-3ea7-417b-bc9c-a009f9766744)
