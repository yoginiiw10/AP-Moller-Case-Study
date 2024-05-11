# Sourcing Cost Forecasting

## Overview
This project aims to forecast sourcing costs for various product combinations using machine learning models. The dataset contains information about the sourcing of different product combinations over a specified time period.

## Dataset
- The dataset comprises rows representing the sourcing of one unit of a particular product combination.
- Each row consists of attributes such as ProductType, Manufacturer, Area Code, Sourcing Channel, Product Size, Product Type, Month of Sourcing, and Sourcing Cost.
- The training set spans from July 2020 to May 2021, while the test set contains data for June 2021.

## Problem Statement
The goal is to iterate on machine learning models to predict sourcing costs accurately for the test set using the training set data.

## Approach
### Exploratory Data Analysis (EDA)
- **Temporal Trends**:
  - Conducted analysis to identify temporal trends in sourcing costs over the study period.
  - Noted that March 2021 exhibited the highest average sourcing cost, indicating increased expenditure during that period. Conversely, September 2020 recorded the lowest average sourcing cost, suggesting potential cost-saving measures or reduced demand.
  
- **Product Size Analysis**:
  - Investigated sourcing costs by product size to understand pricing variations.
  - Observed that "Extra Large" products exhibited the widest range of costs, with occasional outliers exceeding 30,000 units. In contrast, "Large" and "Small" products maintained relatively stable costs below 200 units, indicating consistent pricing trends within these size categories.
  
- **Product Type Analysis**:
  - Analyzed sourcing costs by product type to identify patterns over time.
  - Found that NTM2 consistently had the highest count, followed by NTM1 and then NTM3, suggesting fluctuating popularity among product types, potentially influenced by market demand or product availability.
  
- **Manufacturer Sourcing Strategies**:
  - Explored variations in sourcing strategies among manufacturers.
  - Noted that X1 utilized all available channels for sourcing, indicating a diverse approach. In contrast, X2 was restricted to direct and retail channels, potentially reflecting a targeted sourcing strategy. Lastly, X3 exclusively employed the retail channel, indicating a focused sourcing approach tailored to retail distribution channels.
  
- **Outlier Detection**:
  - Leveraged Isolation Forest as an invaluable tool for handling outliers.
  - Identified and isolated anomalous data points that deviated significantly from the overall distribution of sourcing costs.
  - Demonstrated the impact of outliers on key insights and trends, emphasizing the need for robust outlier detection techniques.
  
- **Seasonality Analysis**:
  - Observed no clear seasonal pattern in the data, indicating the absence of significant seasonal variations.
  - Acknowledged the importance of predictive modeling techniques despite the absence of seasonality and employed the Random Forest Regressor approach for forecasting sourcing costs effectively.

### Forecasting Models
1. **ARIMA Model**
   - **Rationale**: ARIMA (AutoRegressive Integrated Moving Average) models are well-suited for time series forecasting tasks, especially when the data exhibits temporal dependencies and trends. In this project, we utilized the ARIMA model to capture the underlying patterns and seasonality in the sourcing cost data over time. By fitting the ARIMA model to the training data and forecasting future values, we aim to leverage its ability to capture time series dynamics and provide accurate predictions for sourcing costs in June 2021.
   
2. **Random Forest Regressor**
   - **Rationale**: The Random Forest Regressor is a powerful ensemble learning algorithm capable of handling both numerical and categorical data. Given that our dataset contains a mix of numerical and categorical features, the Random Forest Regressor provides a suitable framework for forecasting sourcing costs. By employing techniques such as One-Hot Encoding to handle categorical variables and leveraging the ensemble of decision trees, we can capture complex relationships between features and accurately predict sourcing costs. Additionally, the Random Forest Regressor is robust to outliers and noise in the data, making it a robust choice for this forecasting task.
