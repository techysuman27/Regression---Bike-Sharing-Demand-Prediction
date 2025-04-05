# 🚲 Bike Sharing Demand Prediction - 0.90 %

<b>Problem Statement</b><br>
Currently Rental bikes are introduced in many urban cities for the enhancement of mobility comfort. It is important to make the rental bike available and accessible to the public at the right time as it lessens the waiting time. Eventually, providing the city with a stable supply of rental bikes becomes a major concern. The crucial part is the prediction of bike count required at each hour for the stable supply of rental bikes.<hr>

![Seoul_Bike_Sharing](https://github.com/techysuman27/Regression---Bike-Sharing-Demand-Prediction/assets/160243092/d971f80d-5dd7-4ab7-8e53-31f2e7ab5484)


## 🧾 Project Overview

This project focuses on predicting the **hourly demand** for bike sharing using machine learning regression techniques. Using historical usage data along with weather and temporal features, we aim to develop an accurate prediction model to help optimize operations and improve user experience.

---

## 🎯 Project Objective

- Understand the **key factors** influencing bike rental demand.
- Perform detailed **exploratory data analysis (EDA)** and feature engineering.
- Apply and compare **various regression models**, especially ensemble methods.
- Select the **best-performing model** for robust and reliable predictions.

---

## 📁 Dataset Overview

The dataset consists of **hourly bike rental records**, along with weather and time-related attributes.

| Feature       | Description                                   |
|---------------|-----------------------------------------------|
| `datetime`    | Date and time of the record                   |
| `season`      | Season (1: spring, 2: summer, 3: fall, 4: winter) |
| `holiday`     | Whether the day is a holiday (1: Yes, 0: No)  |
| `workingday`  | If the day is neither weekend nor holiday     |
| `weather`     | Weather condition (1 to 4, 1 being best)      |
| `temp`        | Temperature in Celsius                        |
| `atemp`       | Feels-like temperature                        |
| `humidity`    | Relative humidity                             |
| `windspeed`   | Wind speed                                    |
| `casual`      | Count of casual users                         |
| `registered`  | Count of registered users                     |
| `count`       | Total count of bike rentals (target)          |

### 🔢 Data Shape

- **Rows**: 17,379  
- **Columns**: 12  
- **Missing values**: None

---

## 📊 Exploratory Data Analysis (EDA)

### 🧹 Data Cleaning

- No missing/null values were found.
- Extracted new features from `datetime`:  
  `hour`, `month`, `year`, `weekday`, `day`.
- Dropped `datetime`, `casual`, and `registered` for training.

### 🧪 Feature Engineering

- Extracted useful temporal features:
  - **Hour of the day**
  - **Month & Year**
  - **Weekday**
  - **Is Working Day**
- One-hot encoded categorical features:
  - `season`, `weather`, `hour`, `month`, `weekday`
- Feature Scaling applied to numerical features.

---

## 📈 Key Visual & Statistical Insights

- 🚶‍♂️ **Bike rentals are higher on working days** than weekends.
- 🕗 **Peak rental hours**: Around **8–9 AM** and **6–7 PM** (commute times).
- ☀️ **More rentals during clear weather**, fewer during rainy/snowy conditions.
- 🌡️ **Highest demand between 22°C and 25°C**.
- ❄️ **Winter shows reduced demand**, whereas **summer peaks in usage**.
- 🔧 **Top factors affecting bike demand**:
  - Hour of day  
  - Temperature  
  - Humidity  
  - Wind speed  
  - Visibility  
  - Solar Radiation  
  - Rainfall  
  - Snowfall  
  - Season  
  - Day of the week

---

## 🧠 Machine Learning Pipeline

### 🔍 Data Preparation

- Train-Test Split: **80/20**
- Target variable: `count`
- Applied `log1p()` transformation on the target to handle right-skewed distribution.

### 🤖 Models Trained

| Model                  | R² Score | RMSE     | MAE      |
|------------------------|----------|----------|----------|
| Linear Regression      | 0.393    | 143.19   | 111.54   |
| Ridge Regression       | 0.395    | 143.00   | 111.44   |
| Lasso Regression       | 0.391    | 143.40   | 111.91   |
| Decision Tree Regressor| 0.847    | 64.27    | 44.12    |
| Random Forest Regressor| 0.906    | 50.90    | 37.38    |
| Gradient Boosting      | 0.925    | 44.58    | 32.40    |
| **XGBoost Regressor** (GridSearchCV) | **0.90** | **~42.0** | **~31.0** |

🏆 **Best Model**: **XGBoost Regressor with GridSearchCV**  
✅ Achieved **R² of 0.90**, showing strong generalization and robustness.

---

## 📊 Feature Importance (XGBoost)

| Feature               | Impact       |
|-----------------------|--------------|
| Hour                  | Very High    |
| Temperature           | High         |
| Humidity              | Moderate     |
| Wind Speed            | Moderate     |
| Visibility            | Moderate     |
| Solar Radiation       | Moderate     |
| Rainfall              | Low          |
| Snowfall              | Low          |
| Season                | Moderate     |
| Day of the Week       | Moderate     |

---

## 🔧 Tech Stack & Requirements

**Languages & Tools**:  
- Python (3.7+)
- Libraries:
  - NumPy, Pandas
  - Seaborn, Matplotlib
  - Scikit-learn
  - XGBoost

Install dependencies:

```bash
pip install -r requirements.txt
