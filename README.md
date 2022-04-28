# IntelligentOne
The IntelligentOne is a platform for Model development for the Capital Markets, applying Machine Learning (ML) techniques, Microsoft ML.Net technology, Quantitative techniques, and Sentiment analysis. It automatically performs the data engineering required to calculate the Technical and Fundamentals Indicators, using historical prices, and income, balance sheet and cashflow statements. The AutoML system examines different machine learning algorithms, finds the best algorithm, and build best trained models. The User Interface (UI) combines the charts and trained models to make predictions.

![IntelligentOne UWP App](/images/IntelligentOneScreenshot1.png)

The platform was verified against the following data types: stock, gold, and currency pair instruments.

<img src="./images/IntelligentOneScreenshot0.png" alt="My Project Tickers" width="250" height="150">

### Technical Indicators/Charts
#### Bollinger Bands(BB)
![BB Chart](/images/IntelligentOneScreenshot3.png)

#### Moving Average Convergence Divergence(MACD)
![MACD Chart](/images/IntelligentOneScreenshot4.png)

#### Fast Stochastic Oscillator(FSO) 
![FSO Chart](/images/IntelligentOneScreenshot5.png)

#### Williams %R(%R) 
![WR Chart](/images/IntelligentOneScreenshot6.png)

#### Relative Strength Index(RSI) 
![RSI Chart](/images/IntelligentOneScreenshot7.png)

#### On Balance Volume(OBV)
![OBV Chart](/images/IntelligentOneScreenshot8.png)

#### Moving Average (MA)
![MA Chart](/images/IntelligentOneScreenshot9.png)

#### Average Directional Index(ADX)
![ADX Chart](/images/IntelligentOneScreenshot10.png)

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
 






