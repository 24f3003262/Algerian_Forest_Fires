# Algerian Forest Fires FWI Prediction

## Overview
This project is a machine learning application designed to predict the Fire Weather Index (FWI) based on meteorological data collected from Algerian forest fires. It has been evolved from a data analysis script into a full-fledged web application using Flask, providing a user-friendly interface for making predictions.

This project analyzes the Algerian Forest Fires dataset to understand fire patterns across different regions and builds machine learning regression models to predict the Fire Weather Index (FWI).

## Dataset
The project uses the Algerian Forest Fires Dataset containing 245 records from two regions in Algeria:
- **Bejaia Region**: 122 records
- **Sidi-Bel Abbes Region**: 122 records
- Data collected from June to September 2012.

### Features
- **Temporal**: day, month, year
- **Weather Variables**: Temperature, Relative Humidity (RH), Wind Speed (Ws), Rain
- **Fire Weather Indices**: FFMC, DMC, DC, ISI, BUI, FWI
- **Target**: Classes (Fire/Not Fire)

## Project Workflow

### 1. Data Cleaning (`Algerian Forest FIres analysis.ipynb`)
- Removed rows with missing values
- Dropped duplicate header rows
- Fixed column name spacing issues
- Type conversion: integers for temporal/basic features, floats for weather indices
- Encoded categorical Classes column (0 = Not Fire, 1 = Fire)
- Output: `Algerian_forest_fires_cleaned_dataset.csv`

### 2. Exploratory Data Analysis (EDA)
- Generated distribution histograms for all features
- Class imbalance analysis: Fire vs Not Fire ratio
- Correlation heatmap to identify feature relationships
- Outlier detection using box plots (FWI shows significant positive skew)
- **Monthly Fire Patterns**:
  - *Bejaia*: Peak fire occurrences in August
  - *Sidi-Bel Abbes*: Clear summer peaks in July-August
  - Both regions show decreased fire activity in September

### 3. Feature Engineering & Preprocessing
- Dropped temporal features (day, month, year)
- Multicollinearity assessment with correlation threshold of 0.85
- Feature scaling using `StandardScaler`

### 4. Model Training (`Model Training.ipynb`)
- Regression Models evaluated (Regular and hyperparameter tuned)
- Pickling ML model (`ridgeCV.pkl`) and scaler (`scaler.pkl`)

## Key Findings
- FWI values are concentrated in the lower range (1-12) with outliers extending to higher values
- High fire weather conditions are less frequent but present in the dataset
- Seasonal patterns show distinct peaks during summer months
- Regional differences exist in fire occurrence patterns
- Strong correlations among fire weather indices suggest feature selection is important

## Web Application Features
- **Interactive Web Interface**: A clean, responsive UI built with HTML and CSS.
- **Real-time Prediction**: Users can input weather parameters to get instant FWI predictions.
- **Styled UI**: Features a modern look with gradient backgrounds and card-based layout.

## Tech Stack
- **Frontend**: HTML5, CSS3
- **Backend**: Python, Flask
- **Machine Learning**: Scikit-learn, Pandas, NumPy
- **Tools**: VS Code, Git

## Installation

1. **Clone the repository**
   ```bash
   git clone <repository_url>
   cd Algerian_Forest_Fires
   ```

2. **Create a virtual environment**
   ```bash
   python -m venv .venv
   ```

3. **Activate the virtual environment**
   - On Windows:
     ```bash
     .venv\Scripts\activate
     ```
   - On macOS/Linux:
     ```bash
     source .venv/bin/activate
     ```

4. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

## Usage

1. **Run the application**
   ```bash
   python application.py
   ```

2. **Access the web app**
   Open your web browser and navigate to `http://127.0.0.1:5000`.

3. **Make a Prediction**
   Fill in the required fields (Temperature, RH, Ws, Rain, etc.) and click **Predict** to see the estimated FWI.

## File Structure
- `templates/home.html`: The main HTML page for the input form.
- `static/style.css`: Custom CSS styling for the application.
- `application.py`: The Flask application logic.