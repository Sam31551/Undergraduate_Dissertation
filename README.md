# Researching publicly available data to identify key characteristics of Europe’s most powerful football teams

## Project Overview

This project aims to analyse publicly available data from Europe's top 5 leagues to build, optimize and test predictive models to identify the key characteristics of Europe's most powerful football teams. A team's strength is represented by their squad's transfer value. The goal of this analysis is to offer actionable insights that clubs can take to increase their squad's strength and competitiveness.

## Objectives

-**Data Analysis**: Analyse data from Europe’s top 5 football leagues (England, France, Germany, Italy, Spain).

-**Predictive Modeling**: Build machine learning models to predict a football team's strength based on a variety of features.

-**Optimization**: Use model tuning techniques to improve predictive accuracy and assess the most important features contributing to a team's transfer value.

-**Feature Importance**: Identify the key features that contribute most significantly to a team's strength.

## Installation and Set-Up

1. **Python Installation**: This project requires Python. Ensure you have Python installed on your system. You can download Python from the [official Python website](https://www.python.org/downloads/).

2. **Running Jupyter Notebooks**: The Python files for this project are in `.ipynb` format, which can be executed using Jupyter Notebook or Google Colab. To use Jupyter Notebook locally, you can install it via Anaconda or directly using pip:
   - **Using Anaconda**: Install Anaconda from [Anaconda's website](https://www.anaconda.com/products/distribution) and launch Jupyter Notebook from the Anaconda Navigator.
   - **Using pip**: Install Jupyter Notebook with the command:
     ```bash
     pip install notebook
     ```
     
3. **Required Packages**: This analysis requires several Python packages. You can install these packages using pip. The list of packages and their installation commands are provided below.

   - `pip install pandas`
   - `pip install scikit-learn`
   - `pip install matplotlib`
   - `pip install plotly-express`
   - `pip install numpy`
   - `pip install interpret`
   - `pip install xgboost`
   - `pip install statsmodels`
   - `pip install mlxtend`
   - `pip install shap`
      
Once these packages have been installed all import statements should run.

## Data Source

Data was scraped from globally renowned database website in football, 'Transfermarkt'. Transfermarkt provides detailed statistics on player transfer values, team performance, and other relevant metrics.

## Project Structure

There are 11 python notebooks in the analysis pipeline. The notebooks are intended to be run sequentially, as the outputs from earlier notebooks are required for the subsequent stages.

## Notebooks Overview
#### 1. Data Exploration 
   - Data from the top 5 leagues in Europe is imported. Basic EDA is performed to identify missing data, anomalies and unique values.
   - Data is split by country, unneccessary columns are dropped and column names are standardized. 

#### 2. Data Pre-Processing
   - Teams with consistent missing data are dropped.
   - Rows with missing target values are dopped.
   - Missing data in other columns is imputed.

#### 3. Exploratory Data Analysis 
   - Non-numeric data (i.e. Country, Game outcome) is encoded.
   - Data is explored through the visualisation of variables of interest.
   - A K-Means clustering algorithm is run to classify teams into clusters.
     
#### 4. Feature Engineering
   - A win percentage column is created that represents the team's current perfomance levels.
      
#### 5. Feature Scaling
   - Features were scaled using a MinMax scaler prior to subsequent Machine Learning analysis to ensure uniformity.
     
#### 6. Base Modelling
   - The data is split into training and testing sets and the health of these datasets are checked. 
   - Various baseline regression models, with their default hyperparameters, are run on the data and the results are stored.
     
#### 7. Feature Selection 
   - Feature Subsets are found using Best Subset, Forward and Backward selection techniques.
   - Optimum subsets from each technique are stored for further analysis.
     
#### 8. Models on best variables
   - The regression models from the base modelling stage are retrained on the data subsets created in step 7. These results are stored.

#### 9. Model Optimization 
   - Hyperparameters are optimized using Grid Search and RepeatedKFold cross-validation
   - Optimum model hyperparameters and model results are stored.
     
#### 10. Model Stacking 
   - Optimized models are placed in a stacked model, with Linear Regression as the meta regressor. 
   - The stacked model is trained and evaluated.
     
#### 11. Feature Importance
   - Model results from all previous stages are compared and the best performing model is isolated.
   - SHAP is run using this model.
   - SHAP bar, summary, heatmap and feature importance plots are visualised and interpreted. 


