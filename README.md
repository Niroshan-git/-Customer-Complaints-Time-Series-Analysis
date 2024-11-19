# Customer Complaints Time Series Analysis

## Overview
This project analyzes weekly customer complaints data using various time series forecasting methods, specifically focusing on exponential smoothing techniques. The analysis includes trend and seasonality decomposition, autocorrelation studies, and predictions using Simple, Double, and Triple Exponential Smoothing methods.

## Dataset
The dataset (`weekly_customer_complaints.csv`) contains the following information:
- Weekly customer complaints from 2018 to 2022
- Discount rates
- Commercial events categorized as small, medium, and big

## Requirements
```python
pandas
numpy
matplotlib
statsmodels
scikit-learn
```

## Methodology

### 1. Data Preprocessing
- Loading and parsing dates for time series analysis
- Converting complaint numbers from string (with commas) to float
- Setting weekly frequency (Monday start)

### 2. Exploratory Data Analysis
- Monthly seasonality visualization
- Quarterly seasonality patterns
- Seasonal decomposition (multiplicative model)
- Autocorrelation (ACF) and Partial Autocorrelation (PACF) analysis

### 3. Forecasting Models
Three exponential smoothing methods were implemented:

1. **Simple Exponential Smoothing**
   - Basic smoothing without trend or seasonality

2. **Double Exponential Smoothing**
   - Incorporates trend component
   - Additive trend model

3. **Triple Exponential Smoothing (Holt-Winters)**
   - Incorporates both trend and seasonality
   - Additive trend with multiplicative seasonality
   - Seasonal period: 52 weeks

### 4. Model Evaluation
Models were evaluated using:
- Mean Absolute Error (MAE)
- Root Mean Square Error (RMSE)
- Mean Absolute Percentage Error (MAPE)

Final Model Performance (Holt-Winters):
- MAE: 366.14
- RMSE: 424.83
- MAPE: 8.52%

## Results
The Holt-Winters method (Triple Exponential Smoothing) showed the best performance in capturing both the trend and seasonal patterns in the customer complaints data. This model was used to forecast customer complaints for the next quarter (13 weeks).

## Visualization Examples
The project includes various visualizations:
- Seasonal patterns (monthly and quarterly)
- Time series decomposition
- ACF and PACF plots
- Training vs Test comparisons
- Future predictions

## Usage
1. Clone the repository
2. Install required packages:
```bash
pip install pandas numpy matplotlib statsmodels scikit-learn
```
3. Run the Jupyter notebook or Python script
4. For quick model assessment, use the provided utility functions:
```python
model_assessment(train, test, predictions, chart_title)
plot_future(y, forecast, title)
```

## Future Improvements
- Implementation of other forecasting methods (SARIMA, Prophet)
- Feature engineering with discount rates and commercial events
- Cross-validation for more robust model evaluation
- Interactive dashboard for real-time forecasting

## Contributing
Feel free to fork this repository and submit pull requests with improvements or issue reports.

## License
This project is available under the MIT License.
