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

1.  **🧹Data Cleaning (Pandas):** * Loading raw CSV data and handling missing values or inconsistencies to ensure analysis accuracy.
     Task 1: Data Cleaning and Preparation The objective was to prepare a reliable dataset by addressing missing values and outliers. Missing electricity consumption and cost figures were filled using linear interpolation to preserve time-series trends, while missing occupant counts were imputed with regional medians to maintain realistic household structures without data loss. Additionally, outliers were managed using the Interquartile Range (IQR) method, replacing extreme values with the median to minimize distortion. These steps ensured the final dataset was complete, accurate, and ready for analysis.
    

2.  **🔍Exploratory Data Analysis (NumPy & Pandas):** * Calculating statistical summaries and comparing consumption patterns across different regions.
    * Performing **correlation analysis** to quantify the relationship between the number of occupants and electricity usage.
  Task 2: Exploratory Data Analysis This phase focused on summarizing consumption patterns and validating key relationships. Summary statistics (mean, median, standard deviation) were calculated by region to establish baseline usage trends and variability. A Pearson correlation analysis was then conducted, which confirmed a positive correlation between household size and electricity consumption. This finding empirically justified including the number of occupants as a predictor variable for the subsequent modelling task.

   
3.  **📊Data Visualisation (Matplotlib):** * Generating bar charts to compare regional averages.
    * Creating scatter plots to visualize the impact of household size on energy consumption.
  Task 3: Data Visualisation.Visualisation techniques were applied to uncover underlying trends. **Line graphs** were used to track temporal consumption patterns, while a **multi-line plot** effectively demonstrated consistently higher usage in Urban regions compared to others. Additionally, a **scatter plot** visually confirmed the positive correlation between household size and electricity consumption, reinforcing the statistical findings from Task 2.

   💡 Key Analysis Findings
### 1. Regional Consumption Trends (Time-Series Analysis)
Line charts were generated to track monthly consumption from 2018 to 2022.
* **📈 Seasonal Patterns:**
    * **Peak Usage:** Across all regions, consumption consistently spikes in **March, April, and May**. This correlates with the hottest months of the year, indicating a heavy load from air conditioning and cooling systems.
    * **Troughs:** Usage drops to its lowest points in **September, October, and November**, suggesting cooler weather or a transition period with minimal HVAC reliance.
* **🏙️ Magnitude by Region:**
    * **Urban (Green):** Highest consumption intensity, ranging from **450 to 550 kWh**. This is attributed to high-density living and potentially higher appliance usage.
    * **Suburban (Orange):** Moderate consumption, fluctuating between **350 and 470 kWh**.
    * **Rural (Blue):** Lowest consumption, maintaining a range of **250 to 370 kWh**.
* **Yearly Consistency:** The trends are remarkably stable year-over-year. The overlapping lines indicate that consumption is driven primarily by external environmental factors (seasonality) rather than shifting consumer behavior.

### 2. The Occupancy Anomaly (Scatter Plot Analysis)
* **📉 Negative Correlation:** A scatter plot revealed a counter-intuitive finding: **As household size increases, electricity consumption decreases.**
    * **2-Person Households:** Frequently consume **>500 kWh**.
    * **7-Person Households:** Frequently consume **<300 kWh**.
* **Discussion:** While usually more people equate to higher power usage, this dataset suggests a socioeconomic or structural driver. It implies that larger families may reside in rural, energy-efficient (or non-AC reliant) homes, while smaller households (singles/couples) likely inhabit high-consumption urban apartments with heavy cooling requirements.


4.  **🤖Predictive Modelling (Scikit-Learn):** * Building a **Linear Regression model** to forecast electricity costs (`Cost_RM`).
    * Uses `Consumption_kWh` and `Occupants` as predictor variables to estimate bills with high accuracy.
Task 4: Predictive Modelling A Linear Regression model was developed to predict monthly electricity costs using consumption and occupancy data. This algorithm was chosen due to the direct proportional relationship between usage and cost. The data was split 80:20 for training and testing to ensure unbiased evaluation. Performance was assessed using R-squared and Mean Absolute Error (MAE), yielding strong results that confirmed the model's accuracy. An Actual vs. Predicted plot further validated the model, with data points clustering closely around the perfect prediction line, demonstrating high reliability and low error rates.


💡 Key Analysis Findings
### 📉 Performance Evaluation
The model's performance was evaluated using the **Coefficient of Determination ($R^2$)** and **Mean Absolute Error (MAE)**. The visual analysis of the *Actual vs. Predicted* plot demonstrates exceptional accuracy:

* **Tight Clustering:** The predicted points (blue dots) align almost perfectly along the $y=x$ red dashed line (Perfect Prediction).
* **Low Variance:** There are minimal outliers. For example, at an actual cost of **200 RM**, the model predicts almost exactly **200 RM**.
* **Conclusion:** The high linearity between consumption and cost allowed the Linear Regression model to achieve near-perfect predictive accuracy, making it a reliable tool for forecasting electricity bills based on usage and household data.

 
