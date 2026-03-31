# STC Jawwy TV Data Analysis Project

## Overview
This project analyzes user behavior and content consumption patterns for Jawwy TV using a real dataset. It includes data preprocessing, exploratory analysis, time series forecasting, and a recommendation system.

The main objective is to extract insights, predict future watch trends, and improve user engagement through personalized recommendations.

---

## Dataset
The dataset contains:
- User viewing activity
- Content metadata (movies, series, genres)
- Watch duration
- HD/SD viewing indicator
- Episode and season information

---

## Project Structure
The project is divided into three main parts:

### 1. HD Flag Analysis and User Behavior
- Data cleaning and preprocessing
- Handling missing values
- Aggregation by user and program
- Identifying most watched content and total watch time

### 2. Watch Time Forecasting
- Time series preparation
- Aggregation of watch time over time
- Forecasting using SARIMA model
- Trend analysis

### 3. Recommendation System
- Collaborative filtering approach
- Based on user watch history
- Generates personalized content recommendations

---

## Technologies Used
- Python
- Pandas
- NumPy
- Matplotlib
- Plotly
- Statsmodels (SARIMA)

---

## Data Preprocessing
- Removing unnecessary columns
- Converting data types (e.g., dates)
- Cleaning text fields
- Handling missing values

---

## How to Run
1. Install dependencies:
pip install pandas numpy matplotlib plotly statsmodels pyxlsb

2. Open the notebook:
jupyter notebook

3. Run the notebook cells sequentially.

---

## Results
- Series/Episodes account for **71%** of total watch time (255K hrs) vs Movies (29%)
- SD streaming dominates Series content (**95%** of users), HD more prevalent in Movies (**68%**)
- SARIMA model forecasts daily watch time for 60 future days, peak day: **Friday (794 hrs avg)**
- Collaborative filtering recommendation system built across **11,578 users** and **8,013 programs**
- Interactive Power BI dashboard built to visualize all findings

  ---
  
## Power BI Dashboard
Interactive dashboard covering:
- KPI cards (total watch time, users, peak day)
- Watch time forecast (Actual vs SARIMA)
- HD vs SD breakdown
- Series vs Movies comparison
- Top 5 content recommendations

<img width="1034" height="586" alt="STC Dashboard" src="https://github.com/user-attachments/assets/d22ad5e8-8515-4225-a70e-71dea75beabe" />



---

## Conclusion
This project demonstrates how data analysis and machine learning techniques can be applied to understand user behavior, predict trends, and build recommendation systems in the media streaming domain.
