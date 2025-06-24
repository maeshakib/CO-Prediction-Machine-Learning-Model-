# CO-Prediction-Machine-Learning-Model-
Machine Learning model to predict CO₂ emissions in Rwanda using Sentinel-5P satellite data
Bangladesh Demographics Dashboard, purpose of the analysis is to explore and visualize urban data from Bangladeshi cities, uncovering patterns in population, infrastructure, and socio-economic factors. Using the [Bangladesh Food Prices Dataset
 ]( https://www.kaggle.com/datasets/usmanlovescode/bangladesh-food-prices-dataset) dataset from Kaggle, the Tableau dashboard aims to provide actionable insights for urban planning and policy-making.


 Data set [Link]( https://www.kaggle.com/datasets/msjahid/bangladesh-districts-wise-population).


Tableau Bangladesh Population Dashboard [Link](https://public.tableau.com/views/BangladeshPopulation2022Dashboard/PopDashboard?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link).

 
 Report [Link](https://github.com/maeshakib/z_resources/blob/0dae211943a4a2d212d95f95410295329429f517/DAS%20602%20Assignment%20WFP%20Dashboard%20report%20Student%20ID%20241001661.pdf)

1.1	Background and Context
Monitoring CO₂ is an important area of tackling climate change. Carbon dioxide(CO2 ) is a major GHG gas that makes up 80% of the GHG emissions. Therefore, the reduction of CO2 emissions will help in reducing GHG emissions produced by the county. Accurate forecasting of CO2 emissions is significant in choosing the optimum ways of reducing CO2 emissions. Accurate carbon measurements enable researchers and policymakers to identify sources and patterns of carbon emissions. Developed countries have well-established systems for tracking and monitoring emissions on the ground; such systems are scarce for poor and developing countries. The data for monthly C02 emission is taken from the Kaggle data set “Predict CO2 Emissions in Rwanda”.  The objective of this analysis is “to create a machine learning model using open-source CO2 emissions data from Sentinel-5P satellite observations to predict future carbon emissions.”
These solutions enable governments and other actors to estimate carbon emission levels across Africa, even in places where on-the-ground monitoring is not possible.The open-source CO2 emissions data from Sentinel-5P satellite observations are used by Regression models like Linear, Decision Tree, Random Forest, HistGradient Boosting, Extra Trees, XGB Regressor, and AdaBoost Gradient Boosting models for forecasting CO2 emissions. The performance of the models is compared with each other using RMSE, MAE, and MAPE metrics, and the results show that the Random Forest outperforms all the other models in forecasting CO2 emissions from different sectors. Therefore, the Random Forest model is used to predict future emissions for the next 12 months.
 [MS1] In the First paragraph, provide a brief overview of the field of study, the specific area of machine learning, and the problem you are focusing on. Explaining why this area is important

1.2	Problem Statement
 
1.3	Research Objectives

The primary objective of this research is 
•	To build a machine learning model that predicts CO₂ emissions in Rwanda with high accuracy using open-source CO2 emissions data from Sentinel-5P satellite observations. This study will employ a range of machine learning techniques, including linear and non-linear models, and compare their effectiveness in handling Rwanda's specific data characteristics. 
•	The scope of the research will be confined to CO₂ emissions related to economic and population data, energy consumption, and transportation, aiming to understand which factors have the most significant impact on Rwanda's emission profile. The study will not account for external, unmeasurable factors such as climate policies that may indirectly influence emissions.
•	Comparing the performance of all models to find the best forecasting model.
•	Forecasting the future CO2 emissions using the best model.
•	Publishing the information so that appropriate policies can be implemented.
1.4	Research Questions

The following key research question will be explored:

Which machine learning model is most effective in forecasting Rwanda's future CO₂ emissions using Sentinel-5P satellite data??
This central research question will be supported by the following sub-questions:
•	Which machine learning algorithms perform best in predicting CO₂ emissions with high accuracy in Rwanda?
•	What are the most influential factors contributing to CO₂ emissions in Rwanda based on the models?
•	How well does the best-performing model forecast future CO₂ emissions in Rwanda?
•	How can the findings from this study inform the development of effective policies to mitigate CO₂ emissions in Rwanda?

3.	Research Methodology

3.1	Research Design and Approach



3.3	Data Preprocessing and Cleaning

To ensure the accuracy and consistency of the datasets, data preprocessing and cleaning are essential. This process involves:
•	Data Cleaning: Identification and removal of missing, duplicate, and irrelevant entries.
•	Data Transformation: Conversion of data formats, such as standardizing currency units, converting dates into a unified format.
•	Tools Used: Python libraries such as Pandas, NumPy, seaborn, sklearn, matplotlib are used to clean and merge the data.

•	The dataset has a significant number of missing values. I will handle these missing values by imputing them with the mean for numerical features and the mode for categorical features. I will then check the skewness of the target variable and apply techniques to handle skewness.
•	The skewness of the target variable, emission, is 10.17, indicating a significant right skew. To handle this skewness, I will apply a Box-Cox transformation to the target variable. This transformation will help to normalize the distribution of the target variable, making it more suitable for linear regression models.
•	I have applied the Box-Cox transformation to the target variable, emission. Now, I will split the data into training and testing sets and then apply the models you requested. I will evaluate the performance of each model using RMSE, MAE, and MAPE.
•	I have split the data into training and testing sets. Now, I will apply the models you requested and evaluate their performance using RMSE, MAE, and MAPE.
•	I have removed the ID_LAT_LON_YEAR_WEEK column from the dataset. Now, I will re-run the model training and evaluation process to see if the error is resolved.
•	The raw data cannot be directly used for training the models as it could contain impurities like missing values (NA), special characters or wrong values, therefore, the acquired data is always pre-processed to remove the data impurities. RStudio which is an open source software, was used for cleaning the dataset for the research.


3.4	Exploratory Data Analysis (EDA)

EDA was conducted to understand the underlying patterns, correlations, and distributions in the data. Visualization tools like Power Bl, Tableau, and Python (matplotlib, seaborn) were used to create interactive dashboards and plots. Histogram, scatter plots, and box plots were used to detect outliers, while correlation heatmaps identified the relationships between variables.

•	Statistical Summary of CO2 Emissions: 
•	Mean emission: 81.94
•	Median emission: 45.59
•	High variability (std: 144.30)
•	Range: 0 to 3167.77

#### Feature Correlations:
 
•	The target variable, emission, has weak correlations with most features, as indicated by lighter shades of green and yellow.
•	longitude, Cloud_surface_albedo, and  CarbonMonoxide_CO_column_number_density show weak correlations with the target.

•	UV_AerosolLayerHeight_aerosol_pressure and UV_AerosolLayerHeight_aerosol_height show a strong negative correlation (-0.99), suggesting a strong inverse relationship.
•	All of the features in this dataset have very weak correlations with the emission variable (less than 0.10). This suggests that none of these features, individually, have a strong linear relationship with emissions. To improve prediction or understanding of emissions, you may need to explore other factors or apply more complex models that can capture non-linear relationships.

### Annual Trends: Variation in average CO2 emissions across years


<img align="left" alt="Year Over Year page | PBI" width="1000px" src="https://github.com/maeshakib/z_resources/blob/442e374ac46b7a7d858cf5d6720da2fc8c658e07/trend%20analysis.png" /> <br>


### Key Findings on data cleaning :
I have utilized power query for data cleaning process.
- Header Row Adjustment: Set the first row as the header to correct column naming. ensuring that the column names are accurate and correspond to the data.
- Removing Unnecessary Rows: Removed the first row containing metadata. The first row contained metadata about the dataset, which needed to be removed.
- Column Profiling: Enabled column profiling to check for errors; no errors were found.
- Handling Null or Blank Values: Using column profiling, no significant errors were detected in the dataset under the "Error Value" section
- Data Type Conversion: Converted "latitude" and "longitude" from text to Decimal Number for accurate geospatial mapping. Converted "price" and "usdprice" from text to Decimal Number for proper calculations.
- Renaming Columns: Renamed “admin1” to Division and “admin2” to District for clarity
- Outlier handling: I identified oil price 680 which is far from median 111 BDT, I replaced outlier with median price of the oil.


## Home Page (Power bi Dashboard)
  
<img align="left" alt="Home page | PBI" width="1000px" src="https://github.com/maeshakib/z_resources/blob/d346d67b690eb378384b985e20022e6bfbc776ef/Dashboard%20Home%20Page.png" /> <br>
<br>

### Critical Data Analysis Outcomes from page Year Over Year Comparision

#### 1.Historical Food Price Trends: 
from the market history of Bangladesh we know that
- From 2005-2008 I found food price sharp increase, like Rice from 17.05 BDT to 30.51 BDT, Lentils from 44 to 80 , Oil 39 to 84 and Wheat 19.75 to 39 BDT, as external faction I identified Global - Food Price Surge in 2007–2008, depreciation of the U.S. dollar, export restrictions from the Countries like India and Vietnam impacted food prices during this periods.
- From 2009–2012 also global food crisis significantly impacted Bangladesh, with rice prices peaking at 21–26 BDT per kg in 2012. Oil 60 to 99, Wheat 23 to 37 BDT.
- From 2020–2024: The COVID-19 pandemic and subsequent supply chain disruptions, coupled with global inflation, pushed food prices higher. By 2023–2024, rice prices reportedly reached 41–49 BDT, Oil 79 to 129, Lentils 61 to 115 and Wheat 33 to 54 BDT per kg in some markets, seeing significant increases.

 

 ## CO2 Prediction  (Power bi Dashboard)

<img align="left" alt="Year Over Year page | PBI" width="1000px" src="https://github.com/maeshakib/z_resources/blob/d346d67b690eb378384b985e20022e6bfbc776ef/Dashboard%20Prediction.png" /> <br>
<br>


### Critical Data Analysis Outcomes from page Year Over Year Comparision


#### 1.YoY Price (BDT) Comparison (Division):
- This chart highlights the year-to-year price changes (in BDT) for specific commodities (e.g., wheat, rice, oil, lentils) within a selected Division and Selected Year with previous year.
- It allows users to quickly identify short-term price fluctuations, such as the significant 18.778 BDT drop in oil prices, enabling targeted analysis of market volatility and informing immediate supply chain or pricing adjustments.

 
 

## Used DAX code for analysis
#### 1_YoY_AvgYearSalesDiff =
```
  VAR SelectedYear = VALUE(SELECTEDVALUE(wfp_food_prices_bgd[Year]))
  VAR SelectedDivision = SELECTEDVALUE(wfp_food_prices_bgd[division])
  VAR PrevYear = SelectedYear - 1
  VAR YoY_AvgSalesSelectedYearThisDivision =
  CALCULATE(
  AVERAGE(wfp_food_prices_bgd[price]),
  wfp_food_prices_bgd[Year]=SelectedYear ,
  wfp_food_prices_bgd[division]=SelectedDivision,wfp_food_prices_bgd[pricetype]="Retail"
  )
  VAR YoY_AvgSalesPrevYearThisDivision =
  CALCULATE(
  AVERAGE(wfp_food_prices_bgd[price]),
  wfp_food_prices_bgd[Year]=PrevYear ,
  wfp_food_prices_bgd[division]=SelectedDivision,wfp_food_prices_bgd[pricetype]="Retail"
  )
  RETURN YoY_AvgSalesSelectedYearThisDivision -YoY_AvgSalesPrevYearThisDivision
```
 
