Bangalore Housing Price Prediction
PREDICTING HOUSE PRICES IN BENGALURU
The main aim of this project is to predict the correct housing prices for a given locality in Bangalore using Machine Learning Techniques and Auto ML.

Motivation
What are the things that a potential home buyer considers before purchasing a house? The location, the size of the property, vicinity to offices, schools, parks, restaurants, hospitals, or the stereotypical white picket fence? What about the most important factor - the price?

Let us create a Machine Learning Model which will help us in predicting the prices of the housing prices of a locality in Bangalore on inputting some of the attributes. Here we will be provided with a Data Set containing information about the Housing and their prices.

Super built-up Area: 8790
Built-up Area: 2418
Plot Area: 2025
Carpet Area: 87

Time Line of the Project:
Data Analysis
Feature Engineering
Model Building using ML
Drop features that are not required to build our model

Data Cleaning: Handle NA values
Feature Engineering
Add a new feature (integer) for bhk (Bedrooms Hall Kitchen)
Add a new feature called price per square feet
Examine locations which is a categorical variable. We need to apply dimensionality reduction technique here to reduce the number of locations
Dimensionality Reduction
Any location having less than 10 data points will be tagged as "other" location. This way the number of categories can be reduced by a huge amount. It will help us with having fewer dummy columns.
Outlier Removal Using Logic
Normally, square ft per bedroom is 300 (i.e. a 2 bhk apartment is minimum 600 sqft). For example, a 400 sqft apartment with 2 bhk seems suspicious and can be removed as an outlier. We will remove such outliers by keeping our minimum threshold per bhk to be 300 sqft.
Remove outliers per location using mean and one standard deviation.
Analyzing Property Prices
Check how the 2 BHK and 3 BHK property prices look like for a given location.
Outlier Removal Using Bathrooms Feature
It is unusual to have 2 more bathrooms than the number of bedrooms in a home.
One Hot Encoding For Location
K Fold Cross Validation
Use K Fold cross-validation to measure the accuracy of the LinearRegression model. We can see that in 5 iterations, we get a score above 75% all the time. This is pretty good, but we want to test a few other algorithms for regression to see if we can get an even better score.
Model Selection using GridSearchCV
Ridge Regression:

Best Score: 0.422747
Best Parameters: {'alpha': 0.1}
Lasso Regression:

Best Score: 0.360111
Best Parameters: {'alpha': 1, 'selection': 'random'}
Based on the above analysis, we can conclude that Ridge Regression performs the best among the three models evaluated.

This report provides an overview of the Bangalore Housing Price Prediction project, including data analysis, feature engineering, outlier removal, dimensionality reduction, and model selection. The project aims to predict housing prices in Bangalore using machine learning techniques, providing valuable insights for potential home buyers.