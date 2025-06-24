# CO-Prediction-Machine-Learning-Model-
Machine Learning model to predict CO₂ emissions in Rwanda using Sentinel-5P satellite data
Bangladesh Demographics Dashboard, purpose of the analysis is to explore and visualize urban data from Bangladeshi cities, uncovering patterns in population, infrastructure, and socio-economic factors. Using the [Bangladesh Food Prices Dataset
 ]( https://www.kaggle.com/datasets/usmanlovescode/bangladesh-food-prices-dataset) dataset from Kaggle, the Tableau dashboard aims to provide actionable insights for urban planning and policy-making.


 Data set [Link]( https://www.kaggle.com/datasets/msjahid/bangladesh-districts-wise-population).


Tableau Bangladesh Population Dashboard [Link](https://public.tableau.com/views/BangladeshPopulation2022Dashboard/PopDashboard?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link).

 
 Report [Link](https://github.com/maeshakib/z_resources/blob/0dae211943a4a2d212d95f95410295329429f517/DAS%20602%20Assignment%20WFP%20Dashboard%20report%20Student%20ID%20241001661.pdf)

 
 

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
 
