---
### Overview of Datasets Used for Analysis
---
#### Labour Force Survey 
---
1. Overview:
The Labour Force Survey (LFS) is a monthly survey that provides key labour market indicators, including the unemployment rate, employment rate, and participation rate. It also offers detailed data on employment by industry, occupation, public/private sector, hours worked, wage rates, union status, job permanency, and establishment size. These estimates are available for Canada, provinces, territories, and sub-provincial regions. The LFS is a critical tool for governments, economists, and analysts to evaluate and plan employment programs and policies.

2. Key Applications:
- Labour Market Analysis: Produces unemployment rates, employment rates, and participation rates.
- Policy Planning: Used by Employment and Social Development Canada to determine Employment Insurance (EI) eligibility and benefits.
- Economic Research: Supports labour market analysts, economists, and academics in understanding employment trends and regional disparities.

3. Data Collection:
- Target Population: Includes all individuals aged 15 and older residing in Canada, including non-permanent residents (e.g., work/study permit holders) and permanent residents. Excludes full-time military personnel, institutionalized individuals, and those living on reserves.
- Sampling: Uses a stratified multi-stage design with a rotating panel sample. Approximately 68,000 households are surveyed monthly, covering about 100,000 individuals.
- Data Sources: Data is collected directly from respondents via in-person interviews, telephone interviews, or self-completed electronic questionnaires. Proxy reporting accounts for 65% of responses.
- Reference Period: Data is collected for the week containing the 15th day of the month, with revisions every five years to align with census population estimates.

4. Methodology:
- Sampling Design: A probability-based sample ensures representativeness at national, provincial, and sub-provincial levels.
- Weighting: Sample data are weighted to account for selection probabilities, non-response, and coverage errors. Final weights align with population control totals.
- Imputation: Missing data is addressed using carry-forward, deterministic, and donor imputation methods.

5. Seasonal Adjustment:
- The X-12-ARIMA method is used to seasonally adjust nearly 3,000 LFS series, including national and provincial employment and unemployment estimates.
- Seasonally adjusted data is revised annually for the previous three years to reflect updated seasonal factors.

6. Strengths and Limitations:
- Strengths: Timely, high-frequency data with broad geographic and demographic coverage. Supports detailed cross-classification by industry, occupation, and other characteristics.
- Limitations: Subject to sampling and non-sampling errors. Small sample sizes for sub-provincial regions or specific demographics may reduce reliability.
---
#### Job Vacancies, Payroll Employees, and Job Vacancy Rate by Industry Sector, Monthly, Adjusted for Seasonality
---
1. Overview: The Job Vacancy and Wage Survey (JVWS) provides detailed information on job vacancies in Canada, including the number of vacancies, their characteristics (e.g., full-time vs. part-time, required education/experience), average hourly wages offered, and vacancy duration. Preliminary monthly estimates are available by province/territory and industry sector, while more detailed quarterly data is provided by occupation and economic region. The JVWS serves as the foundational data source for the Job Vacancies, Payroll Employees, and Job Vacancy Rate by Industry Sector, Monthly, Adjusted for Seasonality aggregated dataset, which is used to analyze labour market trends after accounting for seasonal fluctuations.

2. Key Applications:
- Labour Market Analysis: Identifies job vacancy trends and occupational shortages.
- Policy Planning: Supports federal, provincial, and municipal governments in designing employment programs and addressing labour market gaps.
- Economic Research: Provides insights into wage trends, job requirements, and regional labour market dynamics.

3. Data Collection:
- Target Population: Includes all business locations in Canada with at least one paid employee. Excludes religious organizations, private households, and federal/provincial/territorial administrations.
- Sampling: Uses a stratified random sample of approximately 100,000 business locations quarterly, stratified by industry, geography, and size.
- Data Sources: Data is collected directly from employers via an electronic questionnaire. Follow-ups are conducted via email and telephone for non-response.
- Frequency: Monthly preliminary estimates by province/territory and industry; quarterly detailed estimates by occupation and economic region.

4. Methodology:
- Sampling Design: A stratified random sample ensures representation across industries, regions, and business sizes.
- Weighting and Estimation: Initial weights are adjusted for non-response and calibrated to align with employment totals from the Survey of Employment, Payrolls and Hours (SEPH).
- Imputation: Missing data is imputed using a donor approach, where similar responding units provide data for non-responding units.

5. Seasonal Adjustment:
- The Job Vacancy and Wage Survey (JVWS) does not apply seasonal adjustment to its data. However, the aggregated dataset utilized for analysis in this study has been seasonally adjusted to account for recurring fluctuations and to better isolate underlying trends in the labour market.
  
7. Strengths and Limitations:
- Strengths: Provides timely, detailed data on job vacancies and wage trends, supporting labour market analysis and policy development.
- Limitations: Excludes certain sectors (e.g., public administration, religious organizations). Estimates are subject to sampling and non-sampling errors, particularly for smaller regions or industries.
---
#### Consumer Price Index, Monthly, Seasonally Adjusted
---
1. Overview:
The Consumer Price Index (CPI) measures changes in prices of a fixed basket of goods and services over time, reflecting pure price changes experienced by Canadian consumers. It is a key indicator of inflation and is used to adjust payments, deflate economic aggregates, and inform economic policy. The CPI is weighted based on the relative importance of goods and services in consumer expenditures, with annual updates to basket weights derived from Household Final Consumption Expenditure (HFCE) and Survey of Household Spending (SHS) data.

2. Key Applications:
- Escalation of Payments: Adjusts wages, rents, pensions, and social payments to preserve purchasing power.
- Economic Analysis: Used as a deflator for income and expenditure flows, and to monitor inflation and regional price disparities.
- Policy Implementation: Guides the Bank of Canada’s monetary policies.

3. Data Collection:
- Target Population: Urban and rural private households in Canada, excluding collective households, Indigenous reserves, and foreign representatives.
- Sampling: Price data is collected from a representative sample of goods, services, and retail outlets across Canada. Over 1 million price quotes are collected annually.
- Data Sources: Prices are collected from retail outlets, administrative files, and surveys. Transaction data, web scraping, and manual collection are increasingly used.
- Frequency: Most prices are collected monthly, with variations for stable or seasonal items (e.g., annual collection for university tuition fees).

4. Methodology:
- Basket Weights: Expenditure weights are derived from Household Final Consumption Expenditure (HFCE) and Survey of Household Spending (SHS) data, updated annually.
- Index Calculation: A weighted arithmetic average of price changes for elementary aggregates, aggregated to higher levels (e.g., All-items CPI).
- Quality Adjustments: Imputation and hedonic adjustments are used to account for missing data or quality changes in products.

5. Seasonal Adjustment:
- The X-12-ARIMA statistical program is used to seasonally adjust 13 national-level CPI series, including:
    - The All-items CPI.
    - Eight major component indexes (e.g., food, shelter).
    - Four special aggregates (e.g., All-items excluding food and energy).
 
6. Strengths and Limitations:
- Strengths: High accuracy at aggregate levels (e.g., national or major component indexes), strong sampling, and continuous quality enhancements.
- Limitations: Sampling errors may occur due to judgmental sampling methods (except for rents). Accuracy is lower for individual products or smaller geographic areas.
