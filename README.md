#Implementing carry trade in major currency pairs
##Carry trade
Carry trade is a common trading strategy in forex markets where the speculator borrows in a currency that has a low interest rate, and then buys in a currency that offers a high interest rate. The differential between the interest rates of the two different assets is the speculators profit. When using leveraged funds, the opportunities to amplify profits substantially by capturing interest rate gaps.

##Project objectives
The objective of this project was to find the biggest factors affecting the spot rate of a basket of currencies, and build carry trade models using dynamic trade signals, and compare them to thresholds like buy & hold to see whether our trading signal gives us a return

##Data loading 
This dataset was extracted from the Bloomberg terminal during my internship at GIAGCC. In carry trade strategy, it is usual to borrow in a low voltaility market such as the japanese yen to mitigate risk and volatility. Along-side the spot rate of USDCHF, USDEUR, USDINR, USDJPy i have selected the features of current account balances of each country, inflation, and interest rates. 

##Exploratory Data analysis (EDA) '1. Data Cleaning':
in the notebook "1. Data cleaning and preparation" i have cleaned the data and done EDA on log returns to understand volatility. Specifically, the standard deviation of the log return of an asset shows the volatility from a time series. 
![Log returns of a basket of currency pairs](/workspaces/Currency-speculation/output.png)

###EDA conclusions and analyst/quant recommendations
1. During periods of financial crises (GFC), all currency pairs show huge spikes and sharp FX adjustments, particularly USDCHF and USDGBP show particularly large swings, whilst XAUUSD also spikes, which means speculators rush to safe havens like gold to mitigate risk during high volatility
2. During the eurzone debt crises (EDC 2011-2012) noticeable volatility in USDEUR and USDGBP (countries within the eurozone), similar fly to safety in gold evidenced by positive returns in gold

In conclusion, Analyst recommendations say to track gold volatility and log returns as a measure of market sentiment. When Gold prices increase, investor confidence is low and vice versa. 

##calculating differentials
Using the Bloomberg loaded data, i leveraged numpy and pandas in order to calculate feature differentials of different pairs







