# Programming Assignment
### 👤 Group Info:
* Group Name: Dapper Drake
* **Group members:** SHAMNATH GOPI NATHAN, NADTHACHAD VORAVUTH A/L NAI MUNG KUNNURUL, NAJIHAH BINTI NAZRI, YUVINRAJ A/L KOGULE KRISHNAN, NUR ALIYA FARZANA BINTI MOHAMMAD ZAMRI
* **Course:**  SKEE 1033
* **Section:** 17
* **Lecturer:** ASSOC PROF MUHAMMAD MUN`IM AHMAD ZABIDI
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1CScc1jw4PGSCmDxvHLWJkgNIyJ6sKgAm?usp=sharing#scrollTo=2UZr98a3uD2A)
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

The project follows a structured data science workflow to ensure accuracy and reproducibility.

## 🧹 Task 1: Data Cleaning & Preparation (Pandas)
**Objective:** To prepare a reliable dataset by addressing missing values, inconsistencies, and outliers.

* **Handling Missing Values:**
    * **Electricity & Cost:** Filled using **linear interpolation**. This technique was selected to preserve time-series trends and seasonal continuity.
    * **Occupant Counts:** Imputed using **regional medians**. This ensured that household structures remained realistic without discarding valuable data rows.
* **Outlier Management:**
    * Applied the **Interquartile Range (IQR)** method to detect extreme values.
    * Outliers were replaced with the median to minimize statistical distortion while maintaining dataset integrity.

---

## 🔍 Task 2: Exploratory Data Analysis (NumPy & Pandas)
**Objective:** To summarize consumption patterns and validate statistical relationships between variables.

* **Statistical Profiling:** Calculated summary statistics (mean, median, standard deviation) grouped by region to establish baseline usage trends.
* **Correlation Analysis:** Conducted a Pearson correlation analysis to quantify the relationship between household size and electricity usage. This step empirically justified the inclusion of specific features (like occupant count) for the subsequent modelling task.

---

## 📊 Task 3: Data Visualization (Matplotlib)
**Objective:** To uncover underlying trends through visual representation.

* **Visual Techniques:**
    * **Line Graphs:** Used to track temporal consumption patterns over the 5-year period.
    * **Multi-line Plots:** Demonstrated the consumption disparity between Urban, Suburban, and Rural regions.
    * **Scattered Box Plot :** Visualized the correlation between household size and energy consumption.

### 💡 Key Analysis Findings

**1. Regional Consumption Trends (Time-Series)**
* **📈 Seasonal Patterns:**
    * **Peak Usage:** Across all regions, consumption consistently spikes in **March, April, and May**. This correlates with the hottest months, implying heavy reliance on air conditioning.
    * **Troughs:** Usage drops to its lowest in **September, October, and November**, suggesting cooler weather or a transition period with minimal HVAC reliance.
* **🏙️ Magnitude by Region:**
    * **Urban (Green):** Highest consumption (**450–550 kWh**), likely due to high-density living and appliance usage.
    * **Suburban (Orange):** Moderate consumption (**350–470 kWh**).
    * **Rural (Blue):** Lowest consumption (**250–370 kWh**).
* **Yearly Consistency:** Trends are remarkably stable year-over-year, indicating consumption is driven primarily by external factors (seasonality) rather than shifting behavior.

**2. The Occupancy Anomaly (Scatter Plot)**
* **📉 Negative Correlation:** The scatter plot revealed a counter-intuitive finding: **As household size increases, electricity consumption decreases.**
    * *2-Person Households:* Frequently consume **>500 kWh**.
    * *7-Person Households:* Frequently consume **<300 kWh**.
* **Discussion:** This suggests a socioeconomic driver. Larger families in this dataset may reside in rural, energy-efficient (or non-AC reliant) homes, while smaller households (singles/couples) likely inhabit high-consumption urban apartments with heavy cooling requirements.For example larger families(>=5people) residing in
landed properties while smaller families and couples in apartments or condos.As number of occupants increases,the average consumption per person decreases.
---

## 🤖 Task 4: Predictive Modelling (Scikit-Learn)
**Objective:** To build a Linear Regression model to forecast electricity costs (`Cost_RM`).

* **Model Selection:** **Linear Regression** was chosen due to the direct proportional relationship between usage and cost.
* **Training:** Data was split **80:20** for training and testing to ensure unbiased evaluation.
* **Predictors:** Uses Occupants, Month, and Region as the input features to predict the consumption

### 📉1. Predictive Analysis: 

Model vs. Actual Data
Observation:The Linear Regression model acts as a "smoothing" filter over the raw data observed in Task 3.In Task 3 (Actual Data): The scatter plots and line graphs show significant variance (noise). Even for the same month or number of occupants, electricity consumption fluctuates wildly due to unmeasured factors (e.g., individual habits, appliance efficiency).In Task 4 (Model Prediction): The dashed lines (on the monthly graph) and red 'X' marks (on the box plot) represent the expected average behavior. The model successfully captures the seasonal "U-shape" (higher usage in early/late months, lower in the middle) and the linear increase with occupancy.Conclusion:While the model cannot predict random daily spikes (outliers), its high $R^2$ value indicates it is highly reliable for forecasting baseline consumption trends. It confirms that Occupancy and Month are the strongest predictors of electricity usage.

2. Cognitive Analysis: The "Why" Behind the PatternsThis section explains the reasons for the patterns detected by the model.The "Pandemic Effect" (2020–2022): The data likely shows elevated consumption during these years compared to 2018–2019. This is attributed to the COVID-19 Movement Control Orders (MCO). With students and families confined indoors for online classes and remote work, household energy density (lights, AC, computers) increased drastically during daylight hours, which were previously periods of low usage.Seasonal Spikes: The model captures peaks in specific months (likely mid-year or year-end). In the context of Malaysia/tropical climates, this correlates with Monsoon seasons (people staying indoors due to rain) or Heatwaves (increased air-conditioning load).Urban vs. Rural Disparity: The model assigns higher "weights" to Urban regions. This cognitive link suggests that urban households possess more energy-intensive appliances (dryers, multiple AC units, gaming PCs) compared to rural households, even if the number of occupants is the same.

3. Prescriptive Analysis: Recommendations for ActionBased on the predictive trends, we can prescribe specific engineering or policy solutions:For High-Occupancy Homes: Since the model predicts a sharp linear rise in cost for homes with >5 occupants, these households should be targeted for energy audits. Installing smart meters to track real-time usage could help these users identify and reduce waste.Seasonal Load Balancing: Since consumption peaks predictably in specific months, utility providers could introduce Time-of-Use (ToU) tariffs during these peak months, encouraging users to shift heavy usage (like washing machines) to off-peak hours to lower the grid burden.Post-Pandemic Infrastructure: With hybrid study/work becoming the norm (sustaining the 2022 high-usage trend), future housing projects should integrate passive cooling designs (better ventilation, insulation) to reduce the reliance on air-conditioning, which is the primary driver of the consumption identified by the model.
