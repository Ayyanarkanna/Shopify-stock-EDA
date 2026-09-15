# Shopify-stock-EDA

# Shopify Stock Data Analysis

## Project Overview

This project analyzes Shopify stock market data using Python. The dataset is cleaned, transformed, and explored to understand stock price movements and trading volume trends over time.

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib

## Dataset

The project uses a Shopify stock dataset containing:

* Date
* Open Price
* Close Price
* Trading Volume

## Data Preparation

### 1. Import Libraries

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
```

### 2. Load Dataset

```python
df = pd.read_csv("shopify_stock.csv")
```

### 3. Initial Data Inspection

* Display dataset preview using `head()`
* Check column names
* Verify data types
* Review dataset information using `info()`

```python
df.head()
df.info()
df.columns
df.dtypes
```

### 4. Date Conversion

The date column is converted into a datetime format for time-series analysis.

```python
df["date"] = pd.to_datetime(df["date"], utc=True)
```

### 5. Sort Data

Records are sorted chronologically.

```python
df = df.sort_values("date")
```

## Feature Engineering

### Daily Price Change

Calculate the difference between closing and opening prices.

```python
df["Daily_Delta"] = df["close"] - df["open"]
```

### Daily Return Percentage

Calculate the daily stock return percentage.

```python
df["Daily_Return"] = (
    (df["close"] - df["open"]) / df["open"]
) * 100
```

## Data Visualization

### Shopify Closing Price Trend

A line chart is created to visualize the closing stock price over time.

```python
plt.plot(df["date"], df["close"])
```

### Shopify Trading Volume Trend

A line chart is created to analyze trading volume trends.

```python
plt.plot(df["date"], df["volume"])
```

## Key Insights

* Converted stock dates into a proper datetime format.
* Calculated daily stock price changes and returns.
* Identified trends in Shopify closing prices.
* Visualized trading activity using volume data.
* Prepared the dataset for further financial analysis and forecasting.

## Project Outcome

This project demonstrates basic stock market data analysis using Python and provides insights into Shopify's historical stock performance through data preprocessing, feature engineering, and visualization.
