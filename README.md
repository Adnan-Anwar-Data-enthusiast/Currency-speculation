# Implementing carry trade in major currency pairs
## Carry trade
Carry trade is a common trading strategy in forex markets where the speculator borrows in a currency that has a low interest rate, and then buys in a currency that offers a high interest rate. The differential between the interest rates of the two different assets is the speculators profit. When using leveraged funds, the opportunities to amplify profits substantially by capturing interest rate gaps.

## Project objectives
The objective of this project was to find the biggest factors affecting the spot rate of a basket of currencies, and build carry trade models using dynamic trade signals, and compare them to thresholds like buy & hold to see whether our trading signal gives us a return

## Data loading 
This dataset was extracted from the Bloomberg terminal during my internship at GIAGCC. In carry trade strategy, it is usual to borrow in a low voltaility market such as the japanese yen to mitigate risk and volatility. Along-side the spot rate of USDCHF, USDEUR, USDINR, USDJPY i have selected the features of current account balances of each country, inflation, and interest rates. 

## Exploratory Data analysis (EDA) '1. Data Cleaning':
in the notebook "1. Data cleaning and preparation" i have cleaned the data and done EDA on log returns to understand volatility. Specifically, the standard deviation of the log return of an asset shows the volatility from a time series. 
![Log returns of a basket of currency pairs](/workspaces/Currency-speculation/output.png)

### EDA conclusions and analyst/quant recommendations
1. During periods of financial crises (GFC), all currency pairs show huge spikes and sharp FX adjustments, particularly USDCHF and USDGBP show particularly large swings, whilst XAUUSD also spikes, which means speculators rush to safe havens like gold to mitigate risk during high volatility
2. During the eurzone debt crises (EDC 2011-2012) noticeable volatility in USDEUR and USDGBP (countries within the eurozone), similar fly to safety in gold evidenced by positive returns in gold

In conclusion, Analyst recommendations say to track gold volatility and log returns as a measure of market sentiment. When Gold prices increase, investor confidence is low and vice versa. 

##calculating differentials
Using the Bloomberg loaded data, i leveraged numpy and pandas in order to calculate feature differentials of different pairs. 

## Modelling forex pairs
### methodology
1. Cclauclate differences for the features (To ensure normality)
2.  Calculate rolling betas for the features (current account differentials, Interest rate differentials, Inflation differential)
3. Build trading signals by smoothing our rolling betas for each feature
4. Pick up the currency interest signal
5. Test our signal compared to buy & hold

### Results
![USDCHF carry signal results](/workspaces/Currency-speculation/USDCHF trading signal.png)
![USDINR trading signal](/workspaces/Currency-speculation/USDINR trading signal.png)
![USDEUR trading signal](/workspaces/Currency-speculation/USDEUR trading signal.png)
![USDJPY trading signal](/workspaces/Currency-speculation/USDJPY trading signal.png)

# Model Evaluations
## Feature selection
As it is clearly seen, i only picked up the interest rate differentials to develop carry trade signals, but left out all the other features. I shall label this as bottle neck 1. The inability to make profits for all pairs is labelled bottle neck 2
### Bottle neck 1
Bottle neck 1 is the inability to 'mix' all signals to develop a fully fledged trading signal based on factor fundamentals. This may require further model tuning in order to capture signal effectively

### Bottle neck 2
Bottle neck 2 is some pairs performing worse than others. Popular carry strategies such as USDJPY performed a lot better than other pairs, which is likely due to the reason that the interest differentials are very large between them, compared to other pairs such as USDINR that may not be favorable for carry

## Next steps
### Bottle neck 1
One solution to mix all trading signals could be to develop different signals for each pair from their fundamental features, but then to use human intuition to make the trades. This is clearly not fully autonomous, but ensures due diligence is made
### Bottle neck 2
Deep researching into different pairs and what factors usually affect each pair from historical performance. Era checking is also neccesary as trading strategies may differ from each era (Ex:- Pre GFC and post GFC trading strategies for forex)






