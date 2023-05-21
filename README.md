# Bangalore Housing Price Prediction Project

## Overview

The Bangalore Housing Price Prediction project aims to predict the housing prices in Bangalore for a given locality using machine learning techniques. The project involves data analysis, feature engineering, model training, and evaluation.

## Project Structure
The project directory is structured as follows:
.
 * [data](./data)
   * [raw_data](./data/raw_data)
   * [processed_data](./data/processed_data)
 * [notebooks](./notebooks)
   * [Data_Analysis.ipynb](./notebooks/Data_Analysis.ipynb)
   * [Feature_Engineering.ipynb](./notebooks/Feature_Engineering.ipynb)
   * [model_training.ipynb](./notebooks/model_training.ipynb)
 * [scripts](./scripts)
 * [reports](./reports)
   * [report.md](./reports/report.md)
   * [visualizations](./reports/visualizations)
     * [2_3_BHK_plot.png](./reports/visualizations/2_3_BHK_plot.png)
     * [No_Bathroom_plot.png](./reports/visualizations/No_Bathroom_plot.png)
     * [Per_SQ_Feet_plot.png](./reports/visualizations/Per_SQ_Feet_plot.png)
     * [y_test-pred_plot.png](./reports/visualizations/y_test-pred_plot.png)
 * [README.md](./README.md)

- The `data/` directory contains the raw data and processed data subdirectories, where you can store the respective data files.
- The `notebooks/` directory contains Jupyter notebooks for data analysis, feature engineering, and model training.
- The `scripts/` directory can be used to store any additional scripts or code files.
- The `reports/` directory contains the `report.md` file, which provides a detailed report on the project, and the `visualizations/` subdirectory, where you can save any generated visualizations.
- The `README.md` file is the current file you are reading, which provides an overview of the project and its structure.

## Usage

To run the project, follow these steps:

1. Ensure you have the necessary dependencies installed. You can find the required libraries in the Jupyter notebooks under the `notebooks/` directory.
2. Place the raw data files in the `data/raw_data/` directory.
3. Run the Jupyter notebooks in the following order:
   - `Data_Analysis.ipynb` for data analysis and exploration.
   - `Feature_Engineering.ipynb` for feature engineering and preprocessing.
   - `model_training.ipynb` for training and evaluating the machine learning models.
4. The generated visualizations will be saved in the `reports/visualizations/` directory.
5. The final project report will be available in the `reports/report.md` file.

Feel free to explore the project files, modify the code, and adapt it to your specific needs.

# Bangalore Housing Price Prediction

## Predicting House Prices in Bengaluru

The main aim of this project is to predict the correct housing prices for a given locality in Bangalore using Machine Learning Techniques and Auto ML.

### Motivation

What are the things that a potential home buyer considers before purchasing a house? The location, the size of the property, vicinity to offices, schools, parks, restaurants, hospitals, or the stereotypical white picket fence? What about the most important factor - the price?

Let us create a Machine Learning Model which will help us in predicting the prices of the housing prices of a locality in Bangalore on inputting some of the attributes. Here we will be provided with a Data Set containing information about the Housing and their prices.

### Time Line of the Project:

- Data Analysis
- Feature Engineering
- Model Building using ML

## Data Cleaning

### Handle NA values

### Feature Engineering

- Add new feature(integer) for bhk (Bedrooms Hall Kitchen)
- Add new feature called price per square feet
![2_3_BHK_plot](https://github.com/pras-ops/Bangalore-House-Price-Prediction-/assets/56476064/8761a13e-e5be-4085-9245-8ee436f99481)

### Dimensionality Reduction

Examine locations which is a categorical variable. We need to apply dimensionality reduction technique here to reduce the number of locations.

### Outlier Removal Using Logic

- Normally square ft per bedroom is 300 (i.e., 2 bhk apartment is minimum 600 sqft). If a 400 sqft apartment has 2 bhk, then that seems suspicious and can be removed as an outlier. We will remove such outliers by keeping our minimum threshold per bhk to be 300 sqft.
- Remove outliers per location using mean and one standard deviation.
![Per_SQ_Feet_plot](https://github.com/pras-ops/Bangalore-House-Price-Prediction-/assets/56476064/1eb80c35-f990-49cc-b369-8831cbc8b098)

### Outlier Removal Using Bathrooms Feature

It is unusual to have 2 more bathrooms than the number of bedrooms in a home.
![No_Bathroom_plot](https://github.com/pras-ops/Bangalore-House-Price-Prediction-/assets/56476064/e83845bd-9a60-433b-aceb-ddd58a485ed2)


### Use One Hot Encoding For Location

### Use K Fold cross-validation to measure the accuracy of LinearRegression model

We can see that in 5 iterations we get a score above 75% all the time. This is pretty good, but we want to test a few other algorithms for regression to see if we can get an even better score.

### Best Model Results

Based on the grid search, the best model results are as follows:

- Ridge: best score - 0.422747, best params - {'alpha': 0.1}
- Lasso: best score - 0.360111, best params - {'alpha': 1, 'selection': 'random'}


