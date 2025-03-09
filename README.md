# linear-Regression

Here’s a detailed  README  tailored to your linear regression model based on the provided problem statement:

---

#  Demand Prediction for Shared Bikes Using Linear Regression 

    Overview 
This project involves building a  Multiple Linear Regression Model  to predict the demand for shared bikes (`cnt`) based on various factors, including weather conditions, seasons, and user types. The goal is to help BoomBikes, a US-based bike-sharing provider, understand the key factors influencing bike demand and make informed business decisions to recover from revenue losses caused by the COVID-19 pandemic.

---

    Problem Statement 
BoomBikes has experienced significant revenue dips during the ongoing pandemic. To prepare for post-lockdown operations and stand out from competitors, the company aims to:
1. Understand the factors affecting bike demand in the American market.
2. Predict daily bike demand using historical data.
3. Use these insights to optimize their business strategy and meet customer expectations.

The dataset provided includes daily bike rental data along with meteorological and temporal features. The target variable (`cnt`) represents the total number of daily bike rentals, including both casual and registered users.

---

    Business Goal 
The goal of this project is to:
- Identify significant variables that influence bike demand.
- Build a regression model to predict bike demand (`cnt`).
- Provide actionable insights for BoomBikes management to optimize operations and meet demand levels in a new market.

---

    Dataset Description 
  # Source:
The dataset contains daily rental data collected by BoomBikes across the American market.

  # Key Columns:
1.  Independent Variables :
   - `season`: Season of the year (1 = Spring, 2 = Summer, 3 = Fall, 4 = Winter).
   - `yr`: Year (0 = 2018, 1 = 2019).
   - `mnth`: Month of the year (1 to 12).
   - `weathersit`: Weather condition (e.g., clear, cloudy, rainy).
   - `temp`: Normalized temperature in Celsius.
   - `atemp`: Normalized "feels-like" temperature.
   - `hum`: Normalized humidity.
   - `windspeed`: Normalized wind speed.
2.  Target Variable :
   - `cnt`: Total number of bike rentals (sum of casual and registered users).

  # Preprocessing Steps:
- Converted ordinal variables (`season`, `weathersit`) into categorical string values based on labels from the data dictionary.
- Retained the `yr` column as it captures yearly growth in bike demand.
- Dropped irrelevant columns (`casual`, `registered`) since they are already included in `cnt`.

---

    Steps Followed 
  # 1. Data Preparation:
- Handled missing values (if any).
- Converted categorical variables into dummy variables using one-hot encoding.
- Scaled numerical features using standardization techniques.

  # 2. Exploratory Data Analysis (EDA):
- Visualized relationships between features and bike demand using scatter plots, boxplots, and heatmaps.
- Identified trends like seasonal variations, weather effects, and yearly growth in demand.

  # 3. Model Building:
- Built a multiple linear regression model using Python libraries (`sklearn` and `statsmodels`).
- Used `cnt` as the target variable and selected significant predictors based on statistical tests (p-values) and domain knowledge.

  # 4. Model Validation:
- Checked assumptions of linear regression:
  - Linearity: Verified using residual vs. predicted value plots.
  - Normality: Checked residuals using Q-Q plots.
  - Homoscedasticity: Ensured constant variance of residuals across predicted values.
  - No multicollinearity: Verified using Variance Inflation Factor (VIF).
  - Independence of errors: Checked using Durbin-Watson statistic.

  # 5. Model Evaluation:
- Evaluated model performance using metrics like $$ R^2 $$ and Adjusted $$ R^2 $$ on both training and test sets.
- Calculated $$ R^2 $$ for predictions on the test set using:
```python
from sklearn.metrics import r2_score
r2_score(y_test, y_pred)
```

---


    How to Run 
  # Prerequisites:
Install required Python libraries by running:
```bash
pip install -r requirements.txt
```

  # Steps:
1. Clone this repository:
   ```bash
   git clone [repository link]
   ```
2. Open the Jupyter Notebook (`bike_demand_prediction.ipynb`) in your environment.
3. Run all cells sequentially to preprocess data, build the model, validate assumptions, and evaluate performance.



    Contact 
For any questions or feedback, feel free to reach out at sameen.neha@gmail.com.


