# Canada’s Labour Market Dynamics (2021–2024): Inflation, Employment, and Sectoral Disparities

## Project Overview
This project analyzes Canada's labor market from 2021 to 2024, investigating the relationships between unemployment, Inflation, Wages, and Job Vacancy Rates. It leverages predictive modeling techniques to identify critical drivers of Unemployment at national, industry-specific, and demographic levels.

## Project Stages

### 1. Data Loading & Cleaning
- **Labour Force Survey (LFS)**:
  - Loaded and consolidated four years of data.
  - Removed irrelevant features, corrected data formats.
  - Exported a clean dataset.
- **Job Vacancy Data**:
  - Reshaped data, interpolated missing values.
  - Aligned industry categories with LFS.
  - Exported cleaned data.
- **Consumer Price Index (CPI)**:
  - Processed data to isolate relevant inflation measures.
  - Exported clean datasets.

### 2. Exploratory Data Analysis (EDA)
- Generated interactive reports using Sweetviz highlighting key distributions, missingness, and correlations.

### 3. Feature Engineering
- Feature engineered employment rate, unemployment rate, labour force participation rate by survey weights.
- Created lagged indicators, month-over-month and year-over-year inflation rates, market tightness metrics.
- Calculated weighted averages for wages and durations of joblessness at national and industry levels.
- Proportionally adjusted Job Vacancy statistics to match LFS sub-industries

### 4. Trend and Correlation Analysis
- Analyzed time-series trends and correlations among key labor indicators.
- Identified significant relationships and seasonal patterns.

### 5. Industry-Level Analysis
- Conducted detailed industry comparisons.
- Identified top-performing and underperforming sectors using group bar charts, bump charts, and correlation heatmaps.

### 6. Demographic Insights
- Investigated labour market outcomes by gender, age, education, and immigration status.

### 7. Forecasting Labour Market Dynamics (VECM, VAR)
- Developed and compared three time series models — Vector Error Correction Model (VECM), an Vector Autoregression (VAR)
- Applied VAR to model short-run dynamics without assuming cointegration.
- Used VECM to identify long-run cointegrating relationships and model short-run adjustments. 
- Forecasted values for January and February 2025 and compared against actuals.
- Evaluated models using MAE, RMSE, and MAPE to identify the best-performing model per indicator:
  - VECM performed best for forecasting unemployment rate.
  - VAR slightly outperformed others for hourly wage and inflation.

### 8. Predictive Modeling
- Preprocessed data for Logistic Regression, XGBoost, and Random Forest models.
- Fitted classification models to predict industry-level unemployment increases.
- Applied Recursive Feature Elimination with cross-validation (RFECV) and tuned models with RandomSearchCV.
- Compared final models by Accuracy and ROC-AUC metrics.
- Logistic Regression outpreformed XGBoost and Random Forest.

## Repository Contents
- `Data/`: Cleaned datasets (CSV format).
- `Analysis Notebooks/`: Jupyter notebooks organized by analytical stage:
  - `Data_Cleaning_Preprocessing.ipynb`
  - `Bivariate_Multivariate_Analysis.ipynb`
  - `Feature_Engineering.ipynb`
  - `Full_Analysis.ipynb`
  - `Full_Analysis.html`
- `Final Code/`: Final code used for the analysis
  - `Final_Analysis_Code.ipynb`
  - `Final_Analysis_Code.html`
- `EDA Reports/`: Exploratory Data Analysis reports (HTML files).
- `README.md`: This file, summarizing the project's scope and repository organization.

## Tools and Libraries Used
- Python (pandas, numpy, matplotlib, seaborn, statsmodels, scikit-learn, XGBoost, sweetviz)
- Jupyter Notebooks for interactive analysis and documentation



