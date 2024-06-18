# **Problem statement**

Stock price prediction involves forecasting the future price of a company's stock using historical data. 
Accurate predictions can inform trading strategies and investment decisions, aiming to maximize returns or minimize risk.
The objective is to develop a Long Short-Term Memory (LSTM) neural network model to predict future stock prices based on historical data. 

LSTM is chosen due to its ability to capture long-term dependencies and patterns in sequential data.

## **Challenges**

- Volatility: Stock prices are highly volatile and influenced by numerous unpredictable factors such as economic events, market sentiment, and geopolitical issues.
- Complexity: Financial markets are influenced by a myriad of factors including macroeconomic indicators, market trends, and company-specific news.
- Non-linearity: The relationship between past and future prices is non-linear and may include long-term dependencies, making traditional linear models less effective.
- Noise: Financial time series data often contain a significant amount of noise, which can obscure patterns.

## **Considering Historical Data Span: 5 Years vs. 10 Years**

1. Relevance of Market Conditions
### **Market Evolution:** Stock markets evolve over time. Technological advancements, regulatory changes, and shifts in economic conditions can significantly alter market behavior. Data from the last 5 years is more likely to reflect the current market conditions compared to data from 10 years ago.

Corporate Changes: Companies undergo substantial changes over a decade, including shifts in business models, management changes, mergers and acquisitions, which might render older data less relevant.

3. Model Complexity and Training Efficiency
Model Overfitting: Using too much historical data can introduce noise and outdated patterns that are no longer relevant, leading to overfitting. Overfitting occurs when a model learns patterns that are specific to the training data but do not generalize well to unseen data.
Computational Load: Larger datasets increase the computational requirements for training the model. Training on 10 years of data can be significantly more time-consuming and resource-intensive than training on 5 years of data, especially if the data frequency is daily.
4. Availability and Quality of Data
Data Quality: More recent data tends to be of higher quality with fewer missing values and more accurate records. Historical data beyond a certain point might be less reliable due to changes in reporting standards or data collection methods.
Technological Changes: Financial markets have seen significant technological changes in the past decade, including algorithmic trading and the rise of high-frequency trading. Models trained on more recent data are more likely to capture these modern dynamics.
5. Economic Cycles and Trends
Business Cycles: Financial markets are influenced by economic cycles (boom and bust periods). A 5-year span might capture one complete cycle, while a 10-year span could include multiple cycles, making it harder for the model to learn consistent patterns.
Market Sentiment: Investor sentiment and market trends can change over shorter periods. A 5-year window might be more effective in capturing these short-to-medium term trends.
Balancing Act
The choice between using 5 years or 10 years of historical data involves a trade-off:

5 Years: More reflective of current market conditions, lower risk of including outdated patterns, and reduced computational complexity.
10 Years: Broader dataset providing more information, which could be beneficial for capturing long-term trends and reducing the risk of missing significant patterns.
Recommendations
When to Use 5 Years:
The market or company has undergone significant changes in recent years.
The goal is to capture more recent trends and investor behavior.
Limited computational resources are available.
When to Use 10 Years:
The market or company has been relatively stable over the past decade.
The aim is to understand long-term trends and cyclic patterns.
Sufficient computational resources are available to handle the larger dataset.
Practical Approach
Experimentation: Start with 5 years of data. Train the model and evaluate its performance.
Incremental Testing: Gradually include more historical data (e.g., moving to 6, 7, 8 years) and compare the performance. This can help in understanding if additional data improves model accuracy or introduces noise.
Validation: Use cross-validation techniques to assess the model's performance over different periods. This helps in ensuring that the model generalizes well to different market conditions.
By carefully considering these factors and adopting a flexible, experimental approach, you can determine the optimal historical data span for your specific stock price prediction model.






## High Volatile Stocks

- LSTM model excels at capturing patterns in complex data.
- Therefore, LSTM can be better utilised for understanding high volatile instruments.
- High volatily also includes noise ( challenge to overcome)
- Volatility Measurement

### Identify stocks which are volatile enough and provide the measurement
- We can check Standard deviation and Beta measurements
- Find a threshold for choosing the stocks.
- 4 stocks from different segment ( need to research a bit )
- Tech, Finance, Industrial Prod, FMCG


### Notes
- https://www.atlantis-press.com/article/125986767.pdf
- RNN + LSTM Video : https://www.youtube.com/watch?v=6niqTuYFZLQ
