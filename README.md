# LR_final_presentation_Bill_Hannah
 
## Overview
 
This Jupyter Notebook is a practice/learning project that applies **Linear Regression** and **Decision Tree Regression** to a clean, small dataset of car specifications. The goal is to predict **CO₂ emissions** based on engine volume and vehicle weight.
 
---
 
## Dataset
 
- **Source file:** `DATA1.csv`
- **Size:** 36 entries, 5 columns
- **Columns:**
  | Column | Type | Description |
  |--------|------|-------------|
  | Car | object | Car brand (e.g., Mercedes, Ford, BMW) |
  | Model | object | Car model name |
  | Volume | int64 | Engine displacement (cc) |
  | Weight | int64 | Vehicle weight (kg) |
  | CO2 | int64 | CO₂ emissions (target variable) |
 
- **Missing values:** None
 
---
 
## Notebook Structure
 
### 1. Data Loading & Inspection
- Reads the CSV file using `pandas`
- Displays shape, column types, and missing value counts
- Shows value counts for each column
 
### 2. Exploratory Data Analysis (EDA)
- **Bar charts** for car brand and model distributions
- **Histogram** of CO₂ emissions
- **Boxplot** for Weight and Volume
- **Descriptive statistics table** (max, min, quartiles, IQR, mean) for Weight, Volume, and CO₂
- **Scatter plots:** Volume vs. Weight, Volume vs. Car brand, Weight vs. CO₂
- **Correlation matrix** (heatmap) for Volume, Weight, and CO₂
 
### 3. Linear Regression Model
- Features: `Volume`, `Weight`
- Target: `CO2`
- Uses `sklearn.linear_model.LinearRegression`
- Prints the regression equation coefficients and intercept
- Makes a sample prediction for a car with Volume=1300, Weight=2300
 
### 4. Decision Tree Regressor
- Features: `Volume`, `Weight`
- Target: `CO2`
- Uses `sklearn.tree.DecisionTreeRegressor` with `max_leaf_nodes=20`
- Splits data into train/validation sets using `train_test_split`
- Evaluates with **Mean Absolute Error (MAE)**
 
### 5. Random Forest Regressor
- Uses `sklearn.ensemble.RandomForestRegressor`
- Same train/val split as the decision tree
- Also evaluated with MAE for comparison
 
---
 
## Key Findings
 
- **Correlation:**
  - Volume ↔ Weight: ~0.75 (strong positive)
  - Volume ↔ CO₂: ~0.59 (moderate positive)
  - Weight ↔ CO₂: ~0.55 (moderate positive)
 
- **Linear Regression Equation (approximate):**
  ```
  CO2 ≈ 0.0078 × Volume + 0.0076 × Weight + 79.69
  ```
 
- **MAE (Decision Tree & Random Forest):** ~5.38 on validation set
 
---
 
## Dependencies
 
```
pandas
numpy
matplotlib
seaborn
scikit-learn
```
 
---
 
## Notes
 
- This notebook is for **learning/practice purposes** on a clean, small dataset.
- The dataset path is hardcoded (`D:/chenghan/...`) and will need to be updated to run locally.
- No formal train/test split is used for the Linear Regression model (fit on full dataset).
