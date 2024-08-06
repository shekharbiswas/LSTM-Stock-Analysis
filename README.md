# **Problem statement**

Stock price prediction involves forecasting the future price of a company's stock using historical data. 
Accurate predictions can inform trading strategies and investment decisions, aiming to maximize returns or minimize risk.
The objective is to develop a Long Short-Term Memory (LSTM) neural network model to predict future stock prices based on historical data and by doing so, **find the best combination of hyperparameters**. 

LSTM is chosen due to its ability to capture long-term dependencies and patterns in sequential data.

Hyperparameter tuning is quite important step in the development of LSTM (Long Short-Term Memory) models, especially for time-series prediction (e.g., stock price forecasting).
It involves the optimization of various model Hyper-parameters to achieve the best possible performance and hence the best hyperparameters.

**We will be using 3 Hyperparameter tuning techniques for the LSTM model and compare them to choose the best technique.**

Knowing the most effective hyperparameters by applying multiple tuning techniques would be the most demanding task.

## **Challenges**

- Volatility: Stock prices are highly volatile and influenced by numerous unpredictable factors such as economic events, market sentiment, and geopolitical issues.
- Complexity: Financial markets are influenced by a myriad of factors including macroeconomic indicators, market trends, and company-specific news.
- Non-linearity: The relationship between past and future prices is non-linear and may include long-term dependencies, making traditional linear models less effective.
- Noise: Financial time series data often contain a significant amount of noise, which can obscure patterns.

- Computational challenges: Hyperparameter tuning is computationally super expensive. Therefore, upto 300GB of RAM and high speed multi-core GPUs are must.

## **Considering Historical Data Span: 5 Years vs. 10 Years**

### 1. Relevance of Market Conditions
#### **Market Evolution:**

Stock markets evolve over time. Technological advancements, regulatory changes, and shifts in economic conditions can significantly alter market behavior. Data from the last 5 years is more likely to reflect the current market conditions compared to data from 10 years ago.

#### **Corporate Changes:** 
Companies undergo substantial changes over a decade, including shifts in business models, management changes, mergers and acquisitions, which might render older data less relevant.

### 3. Model Complexity and Training Efficiency

#### **Model Overfitting:** 
Using too much historical data can introduce noise and outdated patterns that are no longer relevant, leading to overfitting. 
Overfitting occurs when a model learns patterns that are specific to the training data but do not generalize well to unseen data.

#### **Computational Load:** 
Larger datasets increase the computational requirements for training the model. 
Training on 10 years of data can be significantly more time-consuming and resource-intensive than training on 5 years of data, especially if the data frequency is daily.


### 4. Availability and Quality of Data

#### **Data Quality:**
More recent data tends to be of higher quality with fewer missing values and more accurate records. Historical data beyond a certain point might be less reliable due to changes in reporting standards or data collection methods.
Technological Changes: Financial markets have seen significant technological changes in the past decade, including algorithmic trading and the rise of high-frequency trading. Models trained on more recent data are more likely to capture these modern dynamics.

### 5. Economic Cycles and Trends

#### **Business Cycles:** 
Financial markets are influenced by economic cycles (boom and bust periods). 
A 5-year span might capture one complete cycle, while a 10-year span could include multiple cycles, making it harder for the model to learn consistent patterns.


#### **Market Sentiment:**
Investor sentiment and market trends can change over shorter periods. A 5-year window might be more effective in capturing these short-to-medium term trends.


#### **Balancing Act:**

The choice between using 30 years or 10 years of historical data involves a trade-off:

- 10 Years: More reflective of current market conditions, lower risk of including outdated patterns, and reduced computational complexity.
- 30 Years: Broader dataset providing more information, which could be beneficial for capturing long-term trends and reducing the risk of missing significant patterns.

However, 10 years is a good starting point and then we can decide which time range has more impact.

## **Our strategy**

- **Start with 30 years of data:** Train the model and evaluate its performance.
  
- **Incremental Testing:** Gradually include more historical data (e.g., moving to 6, 7, 8 years) and compare the performance. This can help in understanding if additional data improves model accuracy or introduces noise.
Validation: Use cross-validation techniques to assess the model's performance over different periods. This helps in ensuring that the model generalizes well to different market conditions.
By carefully considering these factors and adopting a flexible, experimental approach, you can determine the optimal historical data span for your specific stock price prediction model.


## Why do we want to choose 'High Volatile' Stocks

- LSTM model excels at capturing patterns in complex data.
- Therefore, LSTM can be better utilised for understanding high volatile instruments.
- High volatily also includes noise ( challenge to overcome)
- Volatility Measurement

### Identify stocks which are volatile enough and provide the measurement
- We can check Standard deviation and Beta measurements
- Find a threshold for choosing the stocks.
- 4 stocks from different segment ( need to research a bit )
- Tech, Finance, Industrial Prod, FMCG



## Why does using only Historical Adj Close price have limitations

Using only historical **adjusted close prices** to predict stock prices in LSTM models has several limitations & problems:

### 1. Limited Information

- Lack of Context: Adjusted close prices alone do not provide information about trading volume, market sentiment, volatility, or any other market dynamics.
- Missed Patterns: Important patterns such as trends, momentum, and cyclic behavior may not be fully captured by just looking at price history.

### 2. Inadequate Volatility Measurement: 

Adjusted close prices alone do not capture market volatility effectively. Indicators like Bollinger Bands or the Average True Range (ATR) provide better insights into market volatility.

### 3. Noise Sensitivity: 

Stock prices sre in general very noisy. Using only adjusted close prices may make it difficult for the model to differentiate between noise and meaningful patterns, leading to poor predictive performance. So additional parameters give enough context to separate noise from actual patterns.

## Benefits of Addl. Technical indicators


Using technical indicators in Long Short-Term Memory (LSTM) models for predicting stock prices can enhance the predictive power and improve the model's performance.

- 1. Additional Information
Technical indicators provide additional information about the market that can be useful for prediction. They summarize various aspects of price movements, trading volume, and market trends, offering insights beyond raw price data.


- 2. Feature Engineering
Incorporating technical indicators is a form of feature engineering, which can significantly enhance the predictive capabilities of machine learning models. Well-chosen indicators can highlight important aspects of the data, providing the LSTM with richer input features.

- 3. Capture Market Sentiment
Many technical indicators are designed to capture market sentiment and momentum, which are critical for making short-term predictions. Indicators like the Relative Strength Index (RSI) and Moving Average Convergence Divergence (MACD) can signal overbought or oversold conditions, helping the model anticipate potential price reversals.

- 4. Trend Detection
Technical indicators can help detect trends and patterns in stock prices that might not be immediately apparent from raw price data. Moving averages, for instance, smooth out price data to highlight trends over different time horizons.

- 5. Reducing Noise
Stock prices can be very noisy and subject to random fluctuations. Technical indicators often smooth out these fluctuations and highlight more meaningful patterns. This can make the data more suitable for LSTM models, which can struggle with extremely noisy data.

- 6. Improving Model Generalization
Using a variety of indicators can help the model generalize better to unseen data. Different indicators can capture different aspects of the market behavior, providing a more holistic view and preventing overfitting to specific patterns in the training data.

- 7. Lagged Effects
Technical indicators inherently incorporate lagged effects of price movements. LSTMs are designed to handle sequential data and dependencies over time, making them well-suited to learn from these lagged relationships provided by the indicators.

However, for this project we will focus mainly on Adj Close Price.

# Project Steps

## 2. Data Collection and Sources
### Historical Stock Data:
- Source: Yahoo Finance or similar financial data APIs.
- Features: Open, High, Low, Close prices, Volume, Adjusted Close.
- Time Period: From January 1, 2015, to March 31, 2023 (example period).

### Technical Indicators:
- Indicators: SMA (Simple Moving Average), EMA (Exponential Moving Average), RSI (Relative Strength Index), MACD (Moving Average Convergence Divergence), - OBV (On-Balance Volume), ATR (Average True Range), Bollinger Bands, ADX (Average Directional Index), CCI (Commodity Channel Index), Williams %R, etc.
- Calculation: Implemented using the ta library or similar Python libraries.

## 4. Integration with LSTM Model
### Data Integration:

- Feature Engineering: Concatenate historical stock data (prices, indicators) with sentiment scores from news articles.
- Time Alignment: Align news sentiment scores with corresponding historical data timestamps.
- LSTM Model Architecture:
- Input Layer: Sequential input of historical data (including technical indicators) and sentiment scores.
- Hidden Layers: Multiple LSTM layers to capture temporal dependencies and patterns.
- Output Layer: Single neuron output for predicting future stock prices.
- Training and Validation:
- Training Data: Split historical data into training and validation sets.
- Model Training: Train LSTM model on historical data with sentiment features.
- Validation: Validate model performance using validation data to ensure robustness.

## 5. Evaluation Metrics and Performance Measures
Metrics: Mean Squared Error (MSE), Mean Absolute Error (MAE), R-squared (R²) for regression evaluation.
Performance: Compare LSTM model performance with and without sentiment features to assess the impact of news sentiment on prediction accuracy.

## 6. Implementation and Tools
- Programming Language: Python.
- Libraries: Pandas, NumPy, TensorFlow/Keras for LSTM, NLTK or SpaCy for text processing, ta for technical indicators.
- Environment: Jupyter Notebook or similar for data exploration, model training, and evaluation.

## 7. Timeline and Milestones
- Week 1-2: Data collection (historical stock data, news articles).
- Week 3: Preprocessing and integration (technical indicators, sentiment analysis).
- Week 4: LSTM model development and training. Hyperparameter Tuning.
- Week 5: Evaluation, fine-tuning, and performance comparison. Report.



### Notes
- https://www.atlantis-press.com/article/125986767.pdf
- RNN + LSTM Video:

[![Watch the video](https://img.youtube.com/vi/6niqTuYFZLQ/maxresdefault.jpg)](https://www.youtube.com/watch?v=6niqTuYFZLQ&list=PLnMKNibPkDnF6-h0x06AATx1kAuBiPRTE)


## Conclusion
To be done ( news, public sentiment etc. could bring more information to LSTM and can do a more accurate job)
