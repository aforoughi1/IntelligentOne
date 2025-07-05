# IntelligentOne
IntelligentOne is an AI-powered platform designed for predictive modelling in capital markets, leveraging machine learning (ML) across technical indicators, financial metrics, and sentiment analysis. It systematically processes vast volumes of historical market data, news articles, balance sheets, and income statements.

The platform performs end-to-end data engineering, constructing relevant indicators and extracting key features that feed into a robust ML modelling pipeline. Powered by AutoML.Net, IntelligentOne dynamically selects and trains the most effective models by evaluating a wide range of machine learning algorithms.

Its intuitive user interface (UI) merges real-time charting with trained model outputs, enhancing analytical depth and supporting data-driven decision-making.

![IntelligentOne UWP App](/images/IntelligentOneScreenshot1.png)

We have implemented several machine learning (ML) models to address key trading strategy questions:
- Is the price action trending in a specific direction?
- Is the trend ending or reversing?
- Are there potential entry or exit points? 
- What are the predicted closing prices for the next five days?
- What is the current market sentiment?
- Is there a potential earnings surprise?

The platform was verified using the following asset classes: stocks, gold, and currency pairs. For example:

<img src="./images/IntelligentOneScreenshot0.png" alt="My Project Tickers" width="250" height="150">

### Technical Indicators/Charts
#### Bollinger Bands(BB)
![BB Chart](/images/IntelligentOneScreenshot3.png)

Bollinger Bands are a way to measure and visualize volatility.

- Closing prices above the upper Bollinger band may indicate that currently the stock price is too high and price may decrease soon. The market is said to be overbought. A Sell signal is generated.
- Closing prices below the lower Bollinger band may be seen as a sign that prices are too low and they may be moving up soon. At this point the market for the stock is said to be oversold. A buy signal is generated.

We apply Multiclass Classification Modelling to predict a potential entry or exit point (Buy/Hold/Sell).

#### Moving Average Convergence Divergence(MACD)
![MACD Chart](/images/IntelligentOneScreenshot4.png)

MACD is used to spot changes in the strength, direction, momentum, and duration of a trend in a stock's
price. We generate a Buy signal when MACD Histogram is positive and Sell signal occurs when moves in the opposite direction.

Binary Classification Modelling is used to predict the trend ending or reversing.

#### Moving Average Crossover (MACO)
![MA Chart](/images/IntelligentOneScreenshot9.png)

We use two averages of different window sizes. The 50-day (a longer-term) moving average is the one that represents the overall trend of the market, while the 20-day (a shorter-term) one represents the more immediate price fluctuation and reacts quicker when the price changes. When the fast MA(20) crosses the slow MA(50) we detect a potential change of trend. 

A signal to buy (as represented by green up-triangle) is triggered when the MA20 cross-overs above the MA50. This shows a shift in trend i.e. the average price over last 20 days has risen above the average price of past 50 days. 

A signal to sell (as represented by red down-triangle) is triggered when cross-under during the opposite movement, indicating that the average price in last 20 days has fallen below the average price of the last 50 days.

Binary Classification Modelling is used to predict the trend ending or reversing.

#### Relative Strength Index(RSI) 
![RSI Chart](/images/IntelligentOneScreenshot7.png)

RSI is a momentum indicator which determines whether the stock is overbought or oversold.
- When the RSI crosses the lower threshold (30) — buy shares, oversold
- When the RSI crosses the upper threshold (70) — sell shares, overbought

We apply Multiclass Classification Modelling to predict a potential entry or exit point (Buy/Hold/Sell).

#### Williams %R(%R) 
![WR Chart](/images/IntelligentOneScreenshot6.png)

W%R is a technical analysis oscillator showing the current closing price in relation to the high and low of the past N days (for a given N).
The oscillator has a range of -100 to 0. Readings below -80 represent oversold territory and readings above -20 represent 
Overbought. At this point, we can start to look for opportunities to trade the stock direction of the cross.

We apply Multiclass Classification Modelling to predict a potential entry or exit point (Buy/Hold/Sell).

#### Stochastic Oscillator(SO) 
![FSO Chart](/images/IntelligentOneScreenshot5.png)

Stochastic Oscillator (SO) is a momentum indicator that compares a stock’s closing price relative to the High-Low range over a given number of trading periods. As a rule, momentum changes before the price changes.

Stochastic %K%D indicator belongs to the oscillators and its value is limited between 0 and 100. Values of %D line that are above 80 indicate that the security is overbought and the values below 20 that it is oversold. Buying and selling entry signals can also be generated when lines %K and %D are intersected: when %K crosses above %D and the value of the oscillator is below oversold(20), buying signal is generated. When the %K crosses below %D and the value of the oscillator is above overbought(80), selling signal is generated.

We apply Multiclass Classification Modelling to predict a potential entry or exit point (Buy/Hold/Sell).

#### Average Directional Index(ADX)
![ADX Chart](/images/IntelligentOneScreenshot10.png)

ADX is an indicator of trend strength in a series of prices of a financial instrument. The following signals are calculated based on the Trend Strength (ADX)  and Trend Direction  (+DI and –DI):
- When +DI is Above -DI then trend is considered as an uptrend. 
- When +DI is Below -DI then trend is considered as a downtrend.
- Trend Strength : IF(ADX > 25,“Buy",“Sell")

Binary Classification Modelling is used to predict if trending in a specific direction and if elevated.

#### On Balance Volume(OBV)
![OBV Chart](/images/IntelligentOneScreenshot8.png)

OBV is a technical analysis indicator intended to relate price and volume in the stock market. The algorithm was used to predict an increase or decrease in Next day closing stock price direction. 

We apply Multiclass Classification Modelling to predict a potential entry or exit point (Buy/Hold/Sell).

#### 5 days Close Price Forecast
Our goal is here to forecast where to set our stop-loss order.

![ndaysforcast](/images/IntelligentOne5DaysForcast.png)

We apply Time Series Forecast /Single Spectrum Analysis (SSA) to series of Price rate-of-change (ROC), which shows the relative difference between the closing price on the day of forecast and the closing price n days previously.

#### The Sentiment Modelling
Sentiment Analysis is, in a nutshell, the process of analysing pieces of text to determine the sentiment, whether they are positive, negative or neutral. Here, it is used to observe the Headlines and Regulatory News, and to determine the tone and the underlying information in source materials. 

To extract the features from the news headlines, we use the natural language processing (NLP) to capture the features in the financial domain. We make use of FinBERT for this task. 

The FinBERT is a Transformer model pretrained fully on financial articles (the language model on a financial corpus). It is further Finetuned using the labelled Financial Sentiment’s dictionary (Financial Phrase Bank by Malo et al. 2014), which has mapped the 
words: sentence | sentiment. The language model is based on the BERT (Bidirectional Encoder Representations) model, a deep neural network, which was developed by Google in 2018.

![The SM App](/images/IntelligentOneSentimentAnalysis1.png)

The result below, it demonstrates the Deep Learning model is exceedingly accurate. 

![The SM Results](/images/IntelligentOneSentimentAnalysis2.png)
 
#### Forecasting Earning Surprises
Many analysts produce earnings estimates for listed companies. The consensus earnings estimate is an average of these estimates. Share prices can move significantly if there are any surprises, such as when actual reported earnings differ greatly from analysts’ estimates.

In order to determine whether a stock falls into Buy, Sell, or Hold classes, we use Single Spectrum Analysis (SSA) to predict the occurrence of earnings surprises. We shown that past earnings (EPS), current analyst forecasts, and differences  between the two are the most important features for predicting future earnings surprises.

![image](/images/IntelligentOneEarningSurprises.png)

### The Model Builder
The ML model builder is a console application which is configurable and implements our Modelling Methodology. It creates a factory for each instrument and uses the AutoML.Net to build/train/evaluate the best model for each indicator. The Modelling Methodology uses template based design pattern for each ML tasks.

![The MlBuilder](/images/IntelligentOneScreenshot25.png)

![The MlBuilder Config](/images/IntelligentOneScreenshot26.png)

Identifying the right features influences the quality and performance of the ML algorithms.

The Model Builder support the following tools:

#### Data Analysis using BoxPlots
The outliers are data points that diverges far away from other values. We need to detect anomalies when preparing datasets for machine learning models e.g., null values because of public holidays.

![The BoxPlot](/images/IntelligentOneScreenshot16.png)

#### The Pearson Correlation Coefficient
The training data sets can be verified for the correlation between different properties by constructing the Pearson Correlation Coefficients.

![The PCC](/images/IntelligentOneScreenshot17.png)

#### The Linearly Separability test
There are classification algorithms that are designed to separate the data by constructing a linear decision Boundary (hyperplane) to the classes. The data sets can be verified for linearly separability or not by constructing their convex hulls.

![The CH](/images/IntelligentOneScreenshot18.png)










