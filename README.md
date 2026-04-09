# COVID-19 Case Forecasting and Analysis

## Overview

This project focuses on analyzing COVID-19 case trends in India and building a simple forecasting approach using historical 
data.
The main goal was to understand how cases change over time and check whether external factors like human mobility have 
any impact on the spread.
The work is based on the given assignment where the task was to clean and combine different datasets, study patterns
and build a model to predict future cases.

---

## Dataset Used

The following datasets were used in this project:

- COVID-19 case data (global time-series dataset)
- Google Mobility data

Both datasets were cleaned and merged based on date so that they can be used together for analysis.
The datasets were integrated using the date column to align COVID case data with mobility patterns for combined analysis.

---

## What I Did

### 1. Data Preprocessing

- Converted COVID data from wide format to long format.
- Filtered data for India.
- Identified that case values were cumulative.
- Converted cumulative cases into daily cases.

This step was important because raw data was not directly usable for analysis.

---

### 2. Feature Creation

To improve the model, I created some new features:

- Previous day cases (to capture dependency on past values)
- 3-day rolling average (short-term trend)
- 7-day rolling average (weekly trend)

Later, mobility features were also added to see if movement patterns affect cases.

---

### 3. Exploratory Analysis

- Observed wave-like patterns in COVID cases.
- Found that data is highly fluctuating and noisy.
- Rolling averages helped in understanding the trend better.
- Distribution analysis showed that data is skewed due to sudden spikes.

---

### 4. Modeling Approach

I built models step by step:

**Baseline Model**
- Used only previous day cases.
- Captured general trend but not spikes.

**Improved Model**
- Added rolling averages.
- Performance improved as trend became clearer.

**Model with Mobility Data**
- Added mobility features to test if movement affects cases.
- Performance did not improve.

**Lagged Mobility Model**
- Added 7-day lag to mobility features.
- Still no improvement.

---

### 5. Model Evaluation

Model performance was evaluated using error metrics such as :
- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)

These metrics helped compare different models and understand how prediction improved after adding new features.

---

## Key Observations

- Time-based features (lag and rolling averages) worked best.
- Mobility data showed some relation but did not help in prediction.
- Adding more features does not always improve the model.
- Data is highly volatile, making prediction difficult.

---

## Assumptions

- COVID data was cumulative and needed conversion to daily values.
- Current cases depend on recent past values.
- Mobility impact may not be immediate (hence lag used).

---

## Limitations

- Used a simple linear model, which cannot capture complex patterns.
- Did not include factors like vaccination, policies or testing rates.
- Mobility impact may require more advanced models.

---

## How to Run the Project

1. Clone this repository
2. Ensure dataset files are present inside the `data/` folder
3. Open the notebook: `covid_forecasting_analysis.ipynb`
4. Run all cells from top to bottom (Restart & Run All)

---

## Project Structure

covid19-forecasting-analysis/
│
├── covid_forecasting_analysis.ipynb
├── covid_analysis_report.pdf
├── data/
│ ├── covid_19_data.csv
│ └── mobility_report.csv

---

## Conclusion

This project shows that understanding the data and creating meaningful features is more important than just adding more data. 
A simple model with the right features performed better than adding extra variables without proper reasoning.

Future work can include using advanced models and adding more real-world factors to improve predictions.

