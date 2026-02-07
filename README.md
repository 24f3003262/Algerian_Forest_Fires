# Algerian Forest Fires Analysis and Prediction

## Project Overview

This project analyzes the Algerian Forest Fires dataset to understand fire patterns across different regions and builds machine learning regression models to predict the Fire Weather Index (FWI).

## Dataset

The project uses the Algerian Forest Fires Dataset containing 245 records from two regions in Algeria:

- Bejaia Region (Region 0): 122 records
- Sidi-Bel Abbes Region (Region 1): 122 records

Data collected from June to September 2012.

### Features

- Temporal: day, month, year
- Weather Variables: Temperature, Relative Humidity (RH), Wind Speed (Ws), Rain
- Fire Weather Indices: FFMC, DMC, DC, ISI, BUI, FWI
- Target: Classes (Fire/Not Fire)

## Project Workflow

1. Data Cleaning (Algerian Forest FIres analysis.ipynb)
- Removed rows with missing values
- Dropped duplicate header rows
- Fixed column name spacing issues
- Type conversion: integers for temporal/basic features, floats for weather indices
- Encoded categorical Classes column (0 = Not Fire, 1 = Fire)
- Output: Algerian_forest_fires_cleaned_dataset.csv

2. Exploratory Data Analysis (EDA)
- Generated distribution histograms for all features
- Class imbalance analysis: Fire vs Not Fire ratio
- Correlation heatmap to identify feature relationships
- Outlier detection using box plots (FWI shows significant positive skew)
- Monthly Fire Patterns:
- - Bejaia: Peak fire occurrences in August
- - Sidi-Bel Abbes: Clear summer peaks in July-August
Both regions show decreased fire activity in September

3. Model Training (Model Training.ipynb)

### Preprocessing

- Dropped temporal features (day, month, year)
- Multicollinearity assessment with correlation threshold of 0.85
- Feature scaling using StandardScaler
- Regression Models evaluated (Regular and hyperparameter tuned)

## Key Findings
- FWI values are concentrated in the lower range (1-12) with outliers extending to higher values
- High fire weather conditions are less frequent but present in the dataset
- Seasonal patterns show distinct peaks during summer months
- Regional differences exist in fire occurrence patterns
- Strong correlations among fire weather indices suggest feature selection is important

## Requirements
See requirements.txt for dependencies.

## Usage
1. Run the analysis notebook first to understand data patterns
2. Run the model training notebook to train and evaluate regression models
3. The cleaned dataset is ready for custom analysis or model development