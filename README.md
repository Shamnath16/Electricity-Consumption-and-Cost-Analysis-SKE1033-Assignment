# Programming Assignment
### 👤 Group Info:
* Group Name: Dapper Drake
* **Group members:** SHAMNATH GOPI NATHAN, NADTHACHAD VORAVUTH A/L NAI MUNG KUNNURUL, NAJIHAH BINTI NAZRI, YUVINRAJ A/L KOGULE KRISHNAN, NUR ALIYA FARZANA BINTI MOHAMMAD ZAMRI
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
    * **Scatter Plots:** Visualized the correlation between household size and energy consumption.

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
* **Discussion:** This suggests a socioeconomic driver. Larger families in this dataset may reside in rural, energy-efficient (or non-AC reliant) homes, while smaller households (singles/couples) likely inhabit high-consumption urban apartments with heavy cooling requirements.

---

## 🤖 Task 4: Predictive Modelling (Scikit-Learn)
**Objective:** To build a Linear Regression model to forecast electricity costs (`Cost_RM`).

* **Model Selection:** **Linear Regression** was chosen due to the direct proportional relationship between usage and cost.
* **Training:** Data was split **80:20** for training and testing to ensure unbiased evaluation.
* **Predictors:** Uses `Consumption_kWh` and `Occupants` to estimate bills.

### 📉 Performance Evaluation
The model's performance was evaluated using the **Coefficient of Determination ($R^2$)** and **Mean Absolute Error (MAE)**.

* **Tight Clustering:** The *Actual vs. Predicted* plot shows predicted points (blue dots) aligning almost perfectly along the $y=x$ red dashed line (Perfect Prediction).
* **Low Variance:** There are minimal outliers. For example, at an actual cost of **200 RM**, the model predicts almost exactly **200 RM**.
* **Conclusion:** The high linearity between consumption and cost allowed the model to achieve near-perfect predictive accuracy, making it a reliable tool for forecasting electricity bills.
