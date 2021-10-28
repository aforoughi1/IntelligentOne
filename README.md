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

