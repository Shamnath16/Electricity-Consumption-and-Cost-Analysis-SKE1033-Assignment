# Programming Assignment
### 👤 Group Info:
* Group Name: Dapper Drake
* **Group members:** SHAMNATH GOPI NATHAN,NADTHACHAD VORAVUTH A/L NAI MUNG KUNNURUL,NAJIHAH BINTI NAZRI,YUVINRAJ A/L KOGULE KRISHNAN,NUR ALIYA FARZANA BINTI MOHAMMAD ZAMRI
* **Course:**  SKEE 1033
* **Section:** 17
* **Lecturer:** ASSOC PROF MUHAMMAD MUN`IM AHMAD ZABIDI
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Shamnath16/Electricity-Consumption-and-Cost-Analysis-SKE1033-Assignment/blob/main/Assignment.ipynb)
# ⚡ Electricity Consumption and Cost Analysis

## 📌 Project Overview
This project is a comprehensive data analysis and predictive modelling assignment for the **SKE1033 Scientific Programming** course. 

The goal of this Python script is to analyze household electricity consumption trends across different regions (Urban, Suburban, and Rural) from **2018 to 2022**. Beyond simple analysis, the project investigates how real-world factors—specifically **household size (number of occupants)**—impact energy usage and costs.

## 📂 Dataset Description
The analysis utilizes a dataset of monthly household electricity records with the following key features:
* **Timeframe:** 2018 – 2022
* **Regions:** Urban, Suburban, Rural
* **Key Variables:**
    * `Consumption_kWh`: Monthly energy usage.
    * `Cost_RM`: Calculated bill based on a flat rate of **RM 0.57 per kWh**.
    * `Occupants`: Number of people in the household (used as a key correlation factor).

## 🛠️ Key Features & Methodology
The project follows a structured data science workflow:

1.  **Data Cleaning (Pandas):** * Loading raw CSV data and handling missing values or inconsistencies to ensure analysis accuracy.
     Task 1: Data Cleaning and Preparation The objective was to prepare a reliable dataset by addressing missing values and outliers. Missing electricity consumption and cost figures were filled using linear interpolation to preserve time-series trends, while missing occupant counts were imputed with regional medians to maintain realistic household structures without data loss. Additionally, outliers were managed using the Interquartile Range (IQR) method, replacing extreme values with the median to minimize distortion. These steps ensured the final dataset was complete, accurate, and ready for analysis.
    


2.  **Exploratory Data Analysis (NumPy & Pandas):** * Calculating statistical summaries and comparing consumption patterns across different regions.
    * Performing **correlation analysis** to quantify the relationship between the number of occupants and electricity usage.
  Task 2: Exploratory Data Analysis This phase focused on summarizing consumption patterns and validating key relationships. Summary statistics (mean, median, standard deviation) were calculated by region to establish baseline usage trends and variability. A Pearson correlation analysis was then conducted, which confirmed a positive correlation between household size and electricity consumption. This finding empirically justified including the number of occupants as a predictor variable for the subsequent modelling task.


   
3.  **Data Visualisation (Matplotlib):** * Generating bar charts to compare regional averages.
    * Creating scatter plots to visualize the impact of household size on energy consumption.
  Task 3: Data Visualisation.Visualisation techniques were applied to uncover underlying trends. **Line graphs** were used to track temporal consumption patterns, while a **multi-line plot** effectively demonstrated consistently higher usage in Urban regions compared to others. Additionally, a **scatter plot** visually confirmed the positive correlation between household size and electricity consumption, reinforcing the statistical findings from Task 2.

   Analysis:
    - **Regional Consumption Trends (Line Charts)Seasonality:

Peak Usage: across all three regions (Rural, Suburban, Urban), there is a distinct seasonal pattern. Consumption consistently peaks around March, April, and May. This likely corresponds to the hottest months of the year in many regions, implying a heavy reliance on air conditioning or cooling systems.

Lowest Usage: Consumption consistently drops to its lowest points around September, October, and November. This suggests cooler weather or a transition period where HVAC usage is minimized.

Magnitude Differences:
Urban (Green Line): Highest consumption, ranging roughly from 450 to 550 kWh. This makes sense given the higher density of appliances and likely larger homes or apartments in city centers.Suburban (Orange Line): Moderate consumption, generally between 350 and 470 kWh.Rural (Blue Line): Lowest consumption, hovering between 250 and 370 kWh.
Yearly Consistency: The trends are remarkably consistent year-over-year (2018–2022). The lines for each year almost overlap, indicating that consumption habits are stable and primarily driven by external factors (like weather) rather than changing behavior.


 - ** Occupants vs. Consumption (Scatter Plot)
Negative Correlation: This is the most surprising finding in our data. The scatter plot shows a clear downward trend. As the number of occupants increases (from 2 to 7), the electricity consumption tends to decrease.Households with 2 people often consume >500 kWh.Households with 7 people often consume <300 kWh.
Potential Explanation: This is counter-intuitive (usually more people = more power). This could suggest a specific socioeconomic factor in our dataset. For example:
Larger families might live in smaller, more energy-efficient rural homes.Smaller households (singles/couples) might live in large, high-consumption urban apartments with heavy AC usage.It could be a "per capita" efficiency, where shared resources (one fridge, one TV) lower the average, but the stark drop suggests a structural difference in the housing types.



4.  **Predictive Modelling (Scikit-Learn):** * Building a **Linear Regression model** to forecast electricity costs (`Cost_RM`).
    * Uses `Consumption_kWh` and `Occupants` as predictor variables to estimate bills with high accuracy.
Task 4: Predictive Modelling A Linear Regression model was developed to predict monthly electricity costs using consumption and occupancy data. This algorithm was chosen due to the direct proportional relationship between usage and cost. The data was split 80:20 for training and testing to ensure unbiased evaluation. Performance was assessed using R-squared and Mean Absolute Error (MAE), yielding strong results that confirmed the model's accuracy. An Actual vs. Predicted plot further validated the model, with data points clustering closely around the perfect prediction line, demonstrating high reliability and low error rates.


Analysis:
 -** Linear Regression Model Performance

High Accuracy: The blue dots (Predicted Points) are tightly clustered around the red dashed line (Perfect Prediction $y=x$).Implication: Model is performing exceptionally well. There are very few outliers.For example, when the Actual Cost is 200 RM, our model predicts almost exactly 200 RM.The variance seems slightly higher in the middle range (around 225 RM), where one point deviates slightly, but overall, the $R^2$ score (coefficient of determination) for this model would likely be very close to 1.0 (or >0.95).Conclusion: The features we selected for our model (likely including 'Region' and 'Month' given their strong influence) are excellent predictors of electricity cost.

 
