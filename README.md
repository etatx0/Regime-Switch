# Markov-Switching chain applied to GJR-GARCH volatilities of Bitcoin

This project aims to use the results found by 
[Ardia, D., Bluteau, K., & Rüede, M. (2019). Regime changes in Bitcoin GARCH volatility dynamics](https://doi.org/10.1016/j.frl.2018.08.009)
to accurately model Regime shifts in the volatility of Bitcoin (_BTC/USD_).

# Status

Further steps include writing a trading-strategy that uses the regime probabilities I've found. Thus far, I have yet to find strategies that _only_ use volatility regimes as input.

# Instructions

## Libraries

* Pandas
* NumPy
* statsmodels
* matplotlib
* ccxt
* arch

## Installation

Clone the repository. You will need Python & Jupyter Notebook to view/edit the MSGARCH_BTCUSD.ipynb file.

To use this model on other cryptocurrencies, you will need to;

__1.__ Ensure the crypto-pair you're looking to test is supported on Binance.

__2.__ Replace the instances of 'BTC/USDT' in the "fetch_ohlcv()", "write_to_csv()", and "refresh_data()" functions to your desired crypto-pair.

__Note:__ Un-commenting & running the "write_to_csv()" function will update the spreadsheet of hourly data. Depending on the crypto-pair/timeframe, 
this step will take a few minutes to run.


# Reflections

I took on this project to aid my understanding of Quant strategies, and familiarize myself with some techniques modern-day Quantitative analysts use.

Initially, I wanted to create a model which could help my understanding of volatility in the Crypto markets, in particular, the BTC/USD pair. This research led me 
to papers & articles on Markov-chains to model regime changes (using returns) and, eventually, to the recent paper by Ardia et al. (2019) which 
noted the effectiveness of GARCH models to forecast volatility when paired with Markov-chains. Seeing that Ardia et al. (2019) had coded their models in R, I 
decided that trying my hand at replicating their findings in Python would be a fun learning exercise.

Currently, I'm looking to find/implement strategies that _purely_ use volatility-regime forecasts to trade futures contracts. With the relatively-young & highly-unpredictable
market of Cryptocurrencies, I believe these MSGARCH models to be the right place to look for alpha.





# Screenshots

![Filtered 2-Regime](https://github.com/tatesh/Regime-Switch/blob/master/visuals/MSGARCH_2_Filtered_BTCUSD.png)

![Smoothed 3-Regime](https://github.com/tatesh/Regime-Switch/blob/master/visuals/MSGARCH_3_Smoothed_BTCUSD.png)
