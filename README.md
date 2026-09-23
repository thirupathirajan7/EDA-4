# Exploratory Data Analysis (EDA) – Shopify Stock

## 📌 Project Overview

This project performs **Exploratory Data Analysis (EDA)** on Shopify stock market data.

The analysis is performed using Python libraries such as **Pandas, NumPy, Matplotlib, and Seaborn**. The main objective is to understand the stock price trends, trading volume, moving averages, and daily returns through data analysis and visualization.

---

## 🎯 Objectives

* Load and inspect Shopify stock data.
* Understand the structure and basic statistics of the dataset.
* Convert and process the date column.
* Analyze Shopify's stock price trends.
* Visualize trading volume over time.
* Calculate 20-day and 50-day moving averages.
* Calculate daily stock returns.
* Analyze the distribution of daily returns.
* Generate meaningful visualizations from the dataset.

---

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Jupyter Notebook / Google Colab

---

## 📂 Dataset

The dataset used in this project is:

`shopify_stock.csv`

The dataset contains Shopify stock market information with columns such as:

* `date` – Date of the stock record
* `open` – Opening stock price
* `high` – Highest stock price
* `low` – Lowest stock price
* `close` – Closing stock price
* `volume` – Number of shares traded

---

## 🔍 EDA Process

### 1. Import Libraries

The following libraries are imported for data manipulation, numerical operations, and visualization:

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```

### 2. Load the Dataset

The Shopify stock CSV file is loaded using Pandas.

```python
df = pd.read_csv("/content/shopify_stock.csv")
df.head()
```

### 3. Understand the Dataset

The dataset is inspected using:

```python
df.info()
df.describe()
df.shape
```

These commands help understand:

* Number of rows and columns
* Data types
* Missing values
* Statistical summary
* Dataset dimensions

### 4. Date Processing

The `date` column is converted into datetime format and the data is sorted chronologically.

```python
df["date"] = pd.to_datetime(df["date"], utc=True)
df = df.sort_values("date")
```

This makes the dataset suitable for time-series analysis.

### 5. Stock Price Trend Analysis

The opening, high, low, and closing prices are plotted against the date to understand how Shopify's stock price changes over time.

The visualization helps identify:

* Overall price movements
* Increasing and decreasing trends
* Changes in stock prices over different periods

### 6. Trading Volume Analysis

Trading volume is visualized over time.

This helps understand how the number of traded shares changes throughout the dataset.

### 7. Moving Average Analysis

Two moving averages are calculated:

* **20-Day Moving Average (MA20)**
* **50-Day Moving Average (MA50)**

```python
df["MA20"] = df["close"].rolling(window=20).mean()
df["MA50"] = df["close"].rolling(window=50).mean()
```

Moving averages help smooth short-term price fluctuations and make the underlying price trend easier to observe.

### 8. Daily Return Calculation

Daily returns are calculated using the percentage change in closing price.

```python
df["Daily_Return"] = df["close"].pct_change()
```

Daily returns show the percentage change in the stock's closing price from one trading day to the next.

### 9. Daily Return Distribution

A histogram with KDE is used to visualize the distribution of daily returns.

```python
sns.histplot(
    df["Daily_Return"].dropna(),
    bins=50,
    kde=True
)
```

This helps understand the spread and distribution of daily stock returns.

---

## 📊 Visualizations

The project includes visualizations such as:

1. Shopify stock price trends
2. Trading volume over time
3. Closing price with moving averages
4. Distribution of daily returns

These visualizations make it easier to identify patterns and trends in the stock data.

---

## 📈 Key Analysis Areas

The EDA focuses on:

* Stock price movement
* Opening and closing prices
* High and low prices
* Trading volume
* Moving averages
* Daily returns
* Distribution of returns
* Time-based stock trends

---

## 💡 Conclusion

This EDA provides an overview of Shopify's historical stock behavior. The analysis uses statistical summaries and visualizations to understand price movements, trading volume, moving averages, and daily returns.

The project demonstrates how Python-based EDA techniques can be used to explore and visualize financial time-series data.

---

## 👩‍💻 Author

**Thirupathi Rajan**

BCA Student

### Tools & Skills

Python | Pandas | NumPy | Matplotlib | Seaborn | Exploratory Data Analysis
