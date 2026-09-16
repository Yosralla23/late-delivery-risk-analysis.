# Late Delivery Risk Analysis

An end-to-end machine-learning project that examines delivery performance and predicts whether an order is likely to be delivered late.

## Overview

Late deliveries can affect customer satisfaction, operational planning, and shipping costs. This project explores historical order data to identify delivery-risk patterns and develops a binary classification workflow for predicting late-delivery risk.

The analysis combines data preparation, exploratory analysis, feature engineering, and time-aware machine-learning practices.

## Objectives

- Explore how late-delivery rates change over time.
- Prepare order-level data for predictive modeling.
- Encode categorical information and scale numerical variables appropriately.
- Build a model that predicts `Late_delivery_risk`.
- Avoid data leakage by respecting the chronological order of the data.

## Workflow

### 1. Data preparation

The dataset was cleaned and prepared for analysis. Date fields were converted to datetime format, and an order-month feature was created for time-based analysis.

### 2. Exploratory data analysis

The monthly late-delivery rate was calculated by grouping orders by month and measuring the percentage of orders marked as late.

The rate remained relatively stable over the observed period, generally ranging from approximately 52% to 58%.

### 3. Feature engineering

Categorical features were transformed with one-hot encoding:

- Shipping Mode
- Market
- Order Region
- Customer Segment

Numerical features were standardized using `StandardScaler`.

### 4. Time-aware modeling

The data was split chronologically rather than randomly. This better reflects a real forecasting setting: the model is trained on earlier orders and evaluated on later orders.

`Late_delivery_risk` was kept separate as the target variable and was not used as an input feature.

## Tools and technologies

- Python
- Pandas and NumPy
- Matplotlib
- Scikit-learn
- Jupyter Notebook
