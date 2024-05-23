# Bike-Sharing-Demand-Prediction - 0.90 %

<b>Problem Statement</b><br>
Currently Rental bikes are introduced in many urban cities for the enhancement of mobility comfort. It is important to make the rental bike available and accessible to the public at the right time as it lessens the waiting time. Eventually, providing the city with a stable supply of rental bikes becomes a major concern. The crucial part is the prediction of bike count required at each hour for the stable supply of rental bikes.<hr>

![Seoul_Bike_Sharing](https://github.com/techysuman27/Regression---Bike-Sharing-Demand-Prediction/assets/160243092/d971f80d-5dd7-4ab7-8e53-31f2e7ab5484)

<strong>Describing DataSet</strong><br>
The dataset contains weather information (Temperature, Humidity, Windspeed, Visibility, Dewpoint, Solar radiation, Snowfall, Rainfall), the number of bikes rented per hour and date information.

<strong>Attribute Information:</strong><br>
Date : year-month-day<br>
Rented_Bike_Count - Count of bikes rented at each hour<br>
Hour - Hour of he day<br>
Temperature-Temperature in Celsius<br>
Humidity - %<br>
Windspeed - m/s<br>
Visibility - 10m<br>
Dew point temperature - Celsius<br>
Solar radiation - MJ/m2<br>
Rainfall - mm<br>
Snowfall - cm<br>
Seasons - Winter, Spring, Summer, Autumn<br>
Holiday - Holiday/No holiday<br>
Functional Day - NoFunc(Non Functional Hours), Fun(Functional hours)<br>
<hr>
<b>Algorithms for Model Training</b>

## Approach
The following steps were followed in the project:
 
**Data Preprocessing**: The dataset was preprocessed and cleaned to handle missing values, outliers, and any inconsistencies in the data.

**Data Split**: The preprocessed data was split into training and test sets. The training set was used to train our machine learning model, while the test set was used for evaluation.

**Model Training**: Several different machine learning model architectures and hyperparameter settings were experimented with. The models were trained using the training data, and their performances were evaluated using various metrics.

**Model Evaluation**: The performance of the trained models was evaluated using metrics such as mean absolute error, root mean squared error, and R-squared. The model that performed the best on the test data was selected.

**Feature Importance**: Ablation studies were conducted to understand the impact of individual features on the model's performance. The analysis revealed the significance of temperature, weather conditions, and seasonality features in predicting bike demand.

**Model Deployment**: The selected model was deployed in a live production setting, where it could make real-time predictions of bike demand. The model's performance was monitored over time to ensure its accuracy and usefulness.
