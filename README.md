# Analyzing Canada's Labour Market Dynamics and the Impact of Inflation: Trends, Disparities, and Predictive Insights for 2024
---
## Project Overview
---

This project aims to explore Ontario’s labour market trends from January to November 2024 by analyzing labour force participation rates, unemployment rates, wage disparities based on population and industry demographics, and the impact of inflation on job vacancies and employment trends. This project focuses on the themes of Predictive Analytics by identifying and understanding patterns over time and uncovering relationships between variables. In addition, this project will follow the theme of Classification and Regression to predict labour
market outcomes based on demographic and economic variables. By exploring the dynamics and the interconnected relationships between datasets, this project aims to provide insights on the effect of inflation on the labour market and the cruciality of understanding the role of the labour market conditions in shaping economic growth and stability.

---
### Project Approach 
---

This analysis will utilize three datasets: the Labour Force Survey (LFS), Job Vacancies and Payroll Employees, and Job Vacancy Rate by Industry Sector, Monthly, Adjusted for Seasonality (JV), and The Consumer Price Index (CPI) dataset. The primary tool for this analysis will be Python through Jupyter Notebook GUI. Key libraries, including Pandas, NumPy, Matplotlib, Seaborn, Plotly, Scikit-learn, Statsmodels, SciPy, and XGBoost, will be used throughout the analysis. 
The project will proceed in several phases, starting with data preprocessing, including handling missing values, checking for duplicates, merging datasets, and feature engineering (e.g., computing the unemployment rate, labour participation rate, and inflation impact). Next, exploratory data analysis (EDA) will be conducted using univariate, bivariate, and multivariate methods, including summary statistics, visualizations (e.g., line graphs, bar charts, box plots, histograms, pair plots, scatter plots), and correlation matrices. Statistical analysis will follow, utilizing parametric and nonparametric tests, along with feature selection techniques such as Principal Component Analysis (PCA) and Recursive Feature Elimination (RFE). Finally, machine learning models will be developed, starting with baseline models and incorporating feature selection. Models like linear regression will predict wage levels and joblessness duration, Random Forest or XGBoost will be used for classification tasks (i.e. predicting the likelihood of unemployment or labour force participation), and Vector Autoregression will be employed for time-series analysis alongside Granger Causality tests to examine the interrelationships between multiple variables over time. Models will be evaluated based on accuracy, precision, recall, F1-score, R-squared, root mean squared error (RMSE) and mean absolute error (MAE) metrics.

---
### Project Questions & Approach 
---
1. What is the labour force participation rate in Ontario from January to October 2024? Are there notable trends, and does inflation have an impact on labour force participation?
2. How do demographic factors such as age, gender, marital status, education level, and type of economic family influence labour force participation?
3. What is the unemployment rate, and how does inflation affect this rate?
4. What is the average duration of joblessness, and how does it vary across demographic groups, industries, and occupations?
5. Are job vacancies associated with higher wages in certain industries? How does inflation influence job vacancy rates across different sectors?
6. Are industries or occupations associated with higher job vacancy rates associated with higher wages? Does inflation impact job vacancy rates in certain industries?
7. How do establishment size and firm size correlate with full-time or part-time employment status?
8. Is there a significant difference between usual hours worked per week and actual hours worked per week? Do workers in certain industries experience longer working hours or more unpaid overtime?
9. On average, how many hours does someone with multiple jobs work per week? How does the distribution of hours differ between usual vs. actual hours for multiple jobholders?
10. Is unpaid overtime more prevalent in specific industries or occupations? Are there patterns between unpaid overtime and demographics?
---
### Current Progress Summary
--- 
LFS Dataset
  - Data cleaning, descriptive statistics was calculated, dataframe was checked for duplicates, and outliers for numerical variables were observed through box plots.
  - Addressed missing values in the dataset
      - All missing values are due to survey design, survey respondents responded to survey questions that are applicable to them.
          - Exception: Variable 'Age of Youngest Child' contained 26% missing data with no clear pattern of which types of economic families was the root. Variable was dropped from                           analysis.
          - Exception: Variables 'Unemployed - used public employment agency, Unemployed - checked with employers directly, Unemployed - checked with friends or relatives,
                       Unemployed - looked at job ads, Unemployed - placed or answered ads, Unemployed - other methods' contained 28% - 87% missing data. Due to the survey design,                            respondents only answered job search questions if the methods applied to them; otherwise, the response was marked as 'not applicable.' Additionally, due to the                         high percentage of missing values, the columns listed above will be excluded from the analysis.
          - Exception: Variable 'Reason for not looking for work during the reference week' contained over 96% missing data. Due to survey data, only respondents not in the labour                            force who said they wanted employment during reference week responded. Due to the extremely high number of missing values,'rsn_not_looking' will be dropped and                         excluded from analysis.
  - Univariate analysis was completed
      - Distribution of categorical variables was observed through count plots.
      - Distribution of numerical variables was observed through histograms.
      - Trends over time were observed for numerical variables through line plots.
      - Trends over time were observed for categorical variables through area charts.
  - Feature Engineering
      -   Variable 'Reference Date' was engineered by combining survey year with survey month to match the formatting of JV and CPI.
      -   Variable 'Monthly Labour Force Participation Rate' was engineered. 'Monthly Labour Force Participation Rate' = (total respondents in the labour force per month/ total                  working age population per month) * 100
      -   Variable 'Monthly Unemployment Rate' was engineered. 'Monthly Unemployment Rate' = (total unemployed respondents/total respondents in the labour force per month) * 100

JV Dataset
  - Data cleaning, descriptive statistics was calculated, transformed dataframe into wide pivot table with variables of interest only, and outliers for numerical variables were observed through box plots.
  - Addressed missing values in the dataset. 2 missing values were observed for the Utilities industry along with 2 missing values were observed for the Information and Cultural         industries. The distributions of each industry was observed for the 'Job Vacancies (#)', and 'Job Vacancy Rate (%)' missing values. Shapiro statistical test was done to confirm normal      distribution and missing values were imputed with the mean.
  - Trends over time were observed 'Job Vacancies (#)', 'Payroll Employees (#)', and 'Job Vacancy Rate (%)' for each industry through sub-line plots.
  - Industries were mapped to LFS and JV dataframe was merged with LFS. 

CPI Dataset
  - Data cleaning, descriptive statistics were calculated, transformed dataframe into wide pivot table with variables of interest only.
  - Feature engineered 'Month over Month Inflation Rate Percentage Change'
  - Trends over time were observed in 'Month over Month Inflation Rate Percentage Change' through line plots.
  - Dataframe was merged with LFS.
---
### Identified Limitations 
--- 
- JV and CPI datasets are adjusted for seasonality; however, LFS is not.
- Industry NAICS codes differ between datasets. LFS dataset uses the 2017 labour variant whereas JV uses the 2022 labour variant. Industries in LFS were spread across a wider range of categories (21 categories) compared to JV (20 categories). In addition, some categories were combined/split differently in LFS and JV.
    - Agriculture, forestry, fishing and hunting [11] in JV is considered one industry. In LFS, they are three separate industries. The overall statistics in JV were used for each         sub-industry. This can obscure important differences in employment trends, job vacancies, and seasonal patterns across the three sectors. This may lead to misinterpretations,          limiting the accuracy of industry-specific insights and comparisons.
    - Manufacturing [31-33] in JV is considered one industry. In LFS, it is split into two categories: Manufacturing - durable goods, and Manufacturing - non-durable goods. The            overall statistics in JV were used for each sub-industry. This can obscure important differences in employment trends, job vacancies, and seasonal patterns across the three            sectors. This may lead to misinterpretations, limiting the accuracy of industry-specific insights and comparisons.
    - Business, building and other support services [55-56] in LFS is one industry. In JV, it is split into two categories: Management of companies and enterprises [55], and               Administrative and support, waste management and remediation services [56]. Statistics between industries Job vacancies (#) and Payroll employees (#) were summed, and a weighted       average was calculated for Job Vacancy Rate (%).
    - Information, culture and recreation [51-71] in LFS is one industry. In JV, it is split into two categories: Information and cultural industries [51], and Arts, entertainment and     recreation [71]. Statistics between industries Job vacancies (#) and Payroll employees (#) were summed, and a weighted average was calculated for Job Vacancy Rate (%).
---
### Professor Abdou's Comments and Addressed Actions 
--- 
- Clarify why the selected period (January–October 2024) was chosen and whether seasonal effects will be considered.
    - Labour Force Survey Dataset along with Consumer Price Index Dataset have data available from January - December 2024. However, Job Vacancies, Payroll Employees, and Job Vacancy      Rate by Industry Sector Dataset is limited to the time frame of January - November 2024. I am hopeful in the next few weeks Statistics Canada will update the dataset to include        December 2024 allowing my analysis to be from January - December of 2024.
    - Initially, the Job Vacancies Dataset only had data for the time frame January - October 2024 but has since been updated on Statistics Canada to include November 2024.
  
- The economic significance of the findings could be better framed. How might policymakers or businesses use these insights?
- Since the study relies on government data, specifying whether the methodology can be easily adapted for future years.
- Are there any missing data concerns, delays in data availability, or biases in self-reported survey responses?
- Why XGBoost vs. Random Forest was chosen for classification?
- Will the analysis control for seasonal effects, given that labour market trends fluctuate throughout the year?
- Would simple statistical models (e.g., ARIMA for time series) be used as a benchmark against ML models?
- Will techniques like GridSearchCV be employed to fine-tune models?

---
### Next Steps
--- 
