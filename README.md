# Stock Data Analysis and Visualization: Tesla and GameStop Case Study

## Overview
This project demonstrates the use of web scraping and the `yfinance` library to extract and visualize revenue and stock data for GameStop (GME) and Tesla (TSLA). The data is plotted using `matplotlib` to showcase historical trends in stock prices and quarterly revenue.

## Requirements
Ensure you have the following Python libraries installed:
- `yfinance`
- `matplotlib`
- `pandas`

You can install these libraries using:
```bash
pip install yfinance matplotlib pandas
```

## Code Explanation

### 1. GameStop Quarterly Revenue Visualization
The following code plots GameStop's quarterly revenue:
```python
import matplotlib.pyplot as plt1

plt1.figure(figsize=(10, 6))
plt1.plot(gme_revenue['Date'], gme_revenue['Revenue'], label='GameStop Quarterly Revenue')
plt1.title("GameStop Quarterly Revenue")
plt1.xlabel('Date')
plt1.ylabel('Revenue (USD)')
plt1.grid(True)
plt1.legend()
plt1.show()
```

### 2. Tesla Stock Price Over Time
This section uses `yfinance` to fetch Tesla's historical stock data and plot it:
```python
import yfinance as yf
import matplotlib.pyplot as plt

tesla = yf.Ticker("TSLA")
tesla_data = tesla.history(period="max")
tesla_data.reset_index(inplace=True)

plt.figure(figsize=(10,6))
plt.plot(tesla_data['Date'], tesla_data['Close'], label='Tesla Stock Price')
plt.title('Tesla Stock Price Over Time')
plt.xlabel('Date')
plt.ylabel('Stock Price (USD)')
plt.grid(True)
plt.legend()
plt.show()
```

### 3. GameStop Stock Price Over Time
Similarly, this section plots GameStop's historical stock data:
```python
import matplotlib.pyplot as plt

gme = yf.Ticker("GME")
gme_data = gme.history(period="max")
gme_data.reset_index(inplace=True)

plt.figure(figsize=(10,6))
plt.plot(gme_data['Date'], gme_data['Close'], label='GameStop Stock Price')
plt.title('GameStop Stock Price Over Time')
plt.xlabel('Date')
plt.ylabel('Stock Price (USD)')
plt.grid(True)
plt.legend()
plt.show()
```

## Usage
1. **GameStop Revenue Data**: Ensure `gme_revenue` is a DataFrame containing 'Date' and 'Revenue' columns for GameStop's quarterly revenue.
2. **Tesla Stock Data**: The script fetches and plots Tesla's historical stock price data.
3. **GameStop Stock Data**: The script fetches and plots GameStop's historical stock price data.

## Results
- The **GameStop Quarterly Revenue** plot shows the revenue trends over time.
- The **Tesla Stock Price Over Time** plot displays Tesla's stock price fluctuations.
- The **GameStop Stock Price Over Time** plot illustrates GameStop's stock price changes.

## Conclusion
This project provides a basic framework for extracting financial data using `yfinance` and visualizing it with `matplotlib`. You can expand this by adding more companies or metrics as needed.

