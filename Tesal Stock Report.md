#### 

#### **Tesla Stock Price Prediction**

#### 

**1. Objective**

The objective of this project is to analyze historical Tesla stock price data and build predictive machine learning models to forecast the closing price of Tesla shares using time-series based features.





**2. Dataset Overview**

Features Used:

Open

High

Low

Close (target variable)

Volume



Index: Date (converted to datetime and sorted chronologically)

&nbsp;      The dataset is structured as a time series, requiring careful handling to avoid data leakage.







**3. Data Preprocessing**

Converted Date column to datetime format

Sorted records by date

Set Date as the index

Selected relevant numerical features only

Handled time dependency using lag features and rolling statistics.







**4. Feature Engineering**

To capture temporal patterns and market momentum, the following features were engineered:



**Lag Features**

Previous closing prices (e.g., Close(t-1), Close(t-2), etc.)



**Rolling Statistics**

Rolling mean of closing price (e.g., 7-day, 14-day averages)

Rolling standard deviation to capture volatility

These features help the models learn trends, seasonality, and short-term price movements.







**5. Train-Test Strategy**

Used TimeSeriesSplit to maintain chronological order

Prevented future data leakage

Ensured realistic evaluation of forecasting performance







**6. Models Implemented**

The following regression models were trained and evaluated:

Linear Regression

Ridge Regression (regularized linear model)

Random Forest Regressor

XGBoost Regressor

For scale-sensitive models, a StandardScaler was applied using a pipeline.







**7. Evaluation Metrics**

Models were evaluated using:

MAE (Mean Absolute Error) – average absolute prediction error

RMSE (Root Mean Squared Error) – penalizes large errors

R² Score – proportion of variance explained

These metrics provide a balanced view of accuracy and robustness.







**8. Results \& Model Performance Insights**

Key Observations:

Tree-based models (Random Forest \& XGBoost) significantly outperformed linear models

Linear and Ridge Regression struggled to capture non-linear price dynamics

XGBoost achieved the best overall performance, indicating strong capability in modeling complex patterns







**9. Feature Importance Analysis**

Using the Random Forest model:

Lagged Close prices were the most influential features

Rolling averages contributed strongly to predictions

Volume had relatively lower importance compared to price-based features

This confirms that historical price movement is the strongest predictor of future prices.







**10. Visual Analysis**

Interactive Plotly charts were used for:

Stock price trends

Feature importance visualization

These visuals improve interpretability and model explainability.





**11. Key Insights Summary**

Tesla stock prices exhibit strong temporal dependency

Machine learning models benefit significantly from lag-based features

Ensemble models are better suited for stock price prediction than linear approaches

Proper time-series validation is critical for reliable evaluation







