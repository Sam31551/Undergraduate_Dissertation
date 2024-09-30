# Researching publicly available data to identify key characteristics of Europe’s most powerful football teams

## Basic Overview

This analysis will consider data from Europe's top 5 leagues to build, optimize and test a predictive model to identify the key characteristics of Europe's most powerful football teams. A team's strength/power is represented by their squad's transfer value. This analysis will provide suggestions that allow clubs to take steps that can increase their squad's strength.


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

Data was scraped from globally renowned database website in football, 'Transfermarkt'.

## Notebooks

There are 11 python notebooks designed to be run in order. Data defined in early notebooks is carried over for analysis in subsequent ones. 

#### 1. Data Exploration 
Data from the top 5 leagues in Europe (England, France, Germany, Italy, Spain) is imported. Unique and interesting min/max vales are found per column. Missing values are checked. 
Data is split by country to ensure consistent structure across regions.
Duplicated columns are dropped and columns are renamed for more intuitive understanding. 
#### 2. Data Pre-Processing
Rows are dropped where target value is null, a team with a whole season's worth of inconsistent data has that season droppped. 
Missing values where values do not change significantly from row to row i.e. average age, are imputed. 
#### 3. Exploratory Data Analysis 
Non-numeric data(i.e. Country, Game outcome) is encoded to allow for subsequent analysis techniques that require numeric data. 
Data is explored through the visualisation of variables of interest. 
A K-Means clustering algorithm is run and the cluster assignments are stored in the dataframe. 
#### 4. Feature Engineering
A win percentage column is created that represents the team's current perfomance levels. 
#### 5. Feature Scaling
Features were scaled using a MinMax scaler prior to subsequent Machine Learning analysis. 
#### 6. Base Modelling
The data is split into training and testing sets and the health of these datasets are checked. 
A range of regression models with their base hyperparameters are run on the data and the results are stored.
#### 7. Feature Selection 
Feature Subsets are found using Best Subset, Forward and Backward selection techniques. Optimum subsets are stored.
#### 8. Models on best variables
Each of the models from stage 6 are run on the data subsets created in step 7. These results are stored. 
#### 9. Model Optimization 
Each of the regression models are optimized using Grid Search cross validation with a RepeatedKFold cross-validation approach. 
Optimum model hyperparameters and model results are stored. 
#### 10. Model Stacking 
Each of the optimized models are placed in a stacked model, with Linear Regression as the meta regressor. The stacked model is trained and tested and the results are stored. 
#### 11. Feature Importance
Model results from all previous stages are compared and the best performing model is isolated. SHAP is run using this model. SHAP bar, summary, heatmap and feature importance plots are visualised and interpreted. 


