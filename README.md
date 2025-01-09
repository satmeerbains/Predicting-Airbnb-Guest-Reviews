# Predicting Airbnb Guest Ratings Using Machine Learning Modeling

## 1. Abstract
This exercise proposes the use of predictive machine learning modeling to estimate the guest ratings at Airbnb stays based on various features. The data is a random sample of a dataframe gathered from stays in the city of London, England on November 5th, 2019. The model contains various features representing the host(s), rules, location, etc and other information of the stay itself. Using machine learning techniques, we develop a model to predict guest ratings with a reasonable level of accuracy. Our findings suggest that certain factors, such as price, location, and host response time, have a significant impact on the ratings given by guests. The results of this study can be valuable for both hosts looking to optimize their listings and platforms like Airbnb seeking to improve guest satisfaction. Findings suggest that certain factors, such as number of previous reviews, price, location, availability, etc have a significant impact on the ratings given by guests. 

## 2. Introduction
Airbnb is an online marketplace where customers can book homestays and experiences in various countries. Each time a guest stays at an accommodation they are encouraged to leave review and a score on the experience. One of the main key performance indicators of how successful a host/stay is the rating. It helps future guests make informed decisions and provides feedback to hosts about their service quality. Predicting guest ratings before a booking can help to better inform hosts on the aspects that lead to customer statisfaction. This paper explores the use of machine learning techniques to predict the ratings that guests would give to Airbnb listings, based on historical data from November 5th 2019. The goal is to develop a model that accurately predicts these ratings and offers insights into the factors that most influence guest satisfaction.

## 3. Data Description
The data contains 106 columns and 39.9 million rows, however a random sample was taken due to computational dependencies. 

The data was gathered from stays in the city of London, England on November 5th, 2019. The source of this data was collected and prepared by Inside Airbnb project (http://insideairbnb.com/)

## 4. Methodology

### 4.1 Data Exploration

Data and necessary libraries were imported. A custom function was created to show the missing data, number of unique values, and the data type for each feature in our dataframe

### 4.2 Data Exploration

#### Formatting features
* Converted features with a $ and % sign to numeric
* Converted date features
* Transformed binary features to boolean for future use
* In preperation for dummy variables categorical values that have a disproportionate value counts were removed

#### Data Cleaning
##### Missing data
* Removed features that have more than 75% missing data since imputation will not help it of any significance in our model.
* Imputation was performed for the rest of the features with missing data

#### Dummy Variables
Dummy variables were created and concatenated to the numeric columns of the dataframe

### 4.3 Feature Selection
#### Finding collinearity and removing redundancies within features
#### Determing multicollinearity Check with Variance Inflation Factor(VIF)
#### Calculating Gini's importance
#### Principal Component Analysis
#### Scaling Data

### 4.4 Building the machine learning model
Built a model of various algorithms that
* Fitted the model first
* Calculate and print the evaluation metrics
* Produced train and test error, with the trained model name with y_predict to then calculate these metrics for all of the models at once.

Regression models Ridge, Decision Tree, RandomForest, XGBoost, LGBM, and MLP were used.

Scalers Standard, MinMax, and no scale were used

Different sets of features were created: full dataset, 40, 20, and 10. Where the selection was made according to Gini's index.

### 4.5 Results
To compare predictions with original values and calculate them between them, three for loops were used inside each other taking values from the dictionaries created, then calculating the RMSE for each of our models

The best performing model was Ridge	regression with 40 selected features (using Gini's importance) with a scaling method of MinMax. It had a RMSE of 6.697556.

### 4.6 Conclusion
This study demonstrates the potential of machine learning to predict Airbnb guest ratings with a relatively high degree of accuracy. The findings highlight the importance of factors such as features such as number of previous reviews, number of rooms available, cleaning fee, price, location, availability in determining guest satisfaction. By leveraging predictive models, both hosts and platform managers can gain valuable insights into the factors driving guest ratings, helping them improve their offerings and enhance user experiences.

Future research could extend this work by incorporating the text based data such as description of the stay, summary etc using natural language processing to gain insight on top phrases/words used in negative or positive reviews. Exploring more advanced machine learning techniques like deep learning models should also be considered
