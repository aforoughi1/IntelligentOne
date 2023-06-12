# IntelligentOne
IntelligentOne is a platform for Model development for the Capital Markets. This innovative solution leverages cutting edge technologies, such as Machine Learning (ML), Microsoft ML.Net, Quantitative and Sentiment analysis techniques. It analyses vast amount of historical market data, News, and companies balance sheet and income statements. It performs data engineering and generates the Technical, Fundamental and Sentiment Indicators as Features, input into the Modelling methodology. By leveraging the power of AutoML.Net, It examines different machine learning algorithms and identifies the best models. The User Interface (UI) combines both charts and trained models allowing for more objective decision making.

![IntelligentOne UWP App](/images/IntelligentOneScreenshot1.png)


We have implemented several ML models based on our trading strategies:
- Regression Predictive Modelling problem (trying to forecast closing price of next day).
- Binary classification problem (price will go up or down).
- The Multiclass classifiers to predict ‘Buy’, ‘Hold’, or ‘Sell’ strategies.
- Time Series forecasting technique using, Single Spectrum Analysis (SSA) algorithm, that can be used to forecast closing price of next N day.


The platform was verified against the following data types: stock, gold, and currency pair instruments. For examples:

<img src="./images/IntelligentOneScreenshot0.png" alt="My Project Tickers" width="250" height="150">

### Technical Indicators/Charts
#### Bollinger Bands(BB)
![BB Chart](/images/IntelligentOneScreenshot3.png)

#### Moving Average Convergence Divergence(MACD)
![MACD Chart](/images/IntelligentOneScreenshot4.png)

#### Moving Average Crossover (MACO)
![MA Chart](/images/IntelligentOneScreenshot9.png)

#### Relative Strength Index(RSI) 
![RSI Chart](/images/IntelligentOneScreenshot7.png)

#### Williams %R(%R) 
![WR Chart](/images/IntelligentOneScreenshot6.png)

#### Fast Stochastic Oscillator(FSO) 
![FSO Chart](/images/IntelligentOneScreenshot5.png)

#### Average Directional Index(ADX)
![ADX Chart](/images/IntelligentOneScreenshot10.png)

#### On Balance Volume(OBV)
![OBV Chart](/images/IntelligentOneScreenshot8.png)

### The Model Builder
The ML model builder is a console application which is configurable. It creates a factory for each instrument and uses the AutoML.Net to build/train/evaluate the best model for each indicator.

![The MlBuilder](/images/IntelligentOneScreenshot25.png)

![The MlBuilder Config](/images/IntelligentOneScreenshot26.png)

Identifying the right features influences the quality and performance of the ML algorithms. The Model Builder support the following tools:

#### Data Analysis using BoxPlots
The outliers are data points that diverges far away from other values. We need to detect anomalies when preparing datasets for machine learning models e.g., null values because of public holidays.

![The BoxPlot](/images/IntelligentOneScreenshot16.png)

#### The Pearson Correlation Coefficient
The training data sets can be verified for the correlation between different properties by constructing the Pearson Correlation Coefficients.

![The PCC](/images/IntelligentOneScreenshot17.png)

#### The Linearly Separability test
There are classification algorithms that are designed to separate the data by constructing a linear decision Boundary (hyperplane) to the classes. The data sets can be verified for linearly separability or not by constructing their convex hulls.

![The CH](/images/IntelligentOneScreenshot18.png)

#### The Sentiment Modelling
Sentiment Analysis is, in a nutshell, the process of analysing pieces of text to determine the sentiment, whether they are positive or negative or neutral. Here, it is used to observe the Headlines and Regulatory News, and to determine the tone and the underlying information in source materials. 

To extract the features from the news headlines, we use the natural language processing (NLP) to capture the features in the financial domain. We make use of FinBERT for this task. 

The FinBERT is a Transformer model pretrained fully on financial articles (the language model on a financial corpus). It is further Finetuned using the labelled Financial Sentiment’s dictionary (Financial Phrase Bank by Malo et al. 2014), which has mapped the 
words: sentence | sentiment. The language model is based on the BERT (Bidirectional Encoder Representations) model, a deep neural network, which was developed by Google in 2018.

![The SM App](/images/IntelligentOneSentimentAnalysis1.png)

The Deep Learning model is 80% accurate. 

![The SM Results](/images/IntelligentOneSentimentAnalysis2.png)
 
#### Forecasting Earning Surprises
Many analysts produce earnings estimates for listed companies. The consensus earnings estimate is an average of these estimates. Share prices can move significantly if there are any surprises, such as when actual reported earnings differ greatly from analysts’ estimates.

In order to determine whether a stock falls into Buy, Sell, or Hold classes, we use machine learning and Time Series Forecast /Single Spectrum Analysis task to predict the occurrence of earnings surprises. We shown that past earnings (EPS), current analyst forecasts, and differences  between the two are the most important features for predicting future earnings surprises.

![image](/images/IntelligentOneEarningSurprises.png)








