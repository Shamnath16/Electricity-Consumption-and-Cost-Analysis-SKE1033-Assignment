# Programming Assignment
### 👤 Group Info:
* Group Name: Dapper Drake
* **Group members:** SHAMNATH GOPI NATHAN,NADTHACHAD VORAVUTH A/L NAI MUNG KUNNURUL,NAJIHAH BINTI NAZRI,YUVINRAJ A/L KOGULE KRISHNAN
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
2.  **Exploratory Data Analysis (NumPy & Pandas):** * Calculating statistical summaries and comparing consumption patterns across different regions.
    * Performing **correlation analysis** to quantify the relationship between the number of occupants and electricity usage.
3.  **Data Visualisation (Matplotlib):** * Generating bar charts to compare regional averages.
    * Creating scatter plots to visualize the impact of household size on energy consumption.
4.  **Predictive Modelling (Scikit-Learn):** * Building a **Linear Regression model** to forecast electricity costs (`Cost_RM`).
    * Uses `Consumption_kWh` and `Occupants` as predictor variables to estimate bills with high accuracy.

## 💻 Technologies Used
* **Python 3.x**
* **Pandas:** For data manipulation and aggregation.
* **NumPy:** For numerical operations.
* **Matplotlib:** For plotting and data visualization.
* **Scikit-Learn:** For training and evaluating the Linear Regression model.


### 📊 Analysis Output
Here is a sample of a linear regression model used for electrical cost prediction

![Graph Description](linear_rgs_output.png)
 
