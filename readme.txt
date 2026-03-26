# Probabilistic Forecasting of Cryptocurrency Returns

This project researches if  adaptive volatility learning improves predictive uncertainty in high-frequency cryptocurrency markets.

Using 1-minute BTC/USD candlestick data from the Coinbase Exchange API, the project compares two one-step-ahead probabilistic forecasting approaches:

- a static baseline with fixed volatility
- a Bayesian model that updates volatility sequentially

Rather than predicting a single next price, the models estimate a predictive distribution for the next return and map that uncertainty back into a price forecast.

## Project Goal

The main goal is to evaluate if adaptive volatility modeling provides better-calibrated uncertainty than a fixed-volatility baseline, especially in noisy and rapidly changing market conditions.

## Repository Contents

- `Proj.ipynb` — main project notebook
- `Proj.html` — exported HTML version of the notebook
- `Proj.pdf` — exported PDF report
- `requirements.txt` — Python dependencies
- `data/` — folder containing the data that was used 

## Requirements

This project requires:

- Python 3.10+
- numpy
- pandas
- matplotlib
- requests

## Data Source

This project uses 1-minute BTC/USD candlestick data from the Coinbase Exchange API.

Each candle contains:
- open
- high
- low
- close
- volume

Only the closing price is used to compute log returns.

## Methods

The analysis includes:

1. collecting and cleaning 1-minute BTC/USD candle data
2. transforming closing prices into log returns
3. estimating a static Gaussian baseline
4. sequentially updating a Bayesian volatility model
5. generating one-step-ahead forecasts with Monte Carlo simulation
6. evaluating predictive performance and uncertainty behavior

## Main Takeaway

Bayesian updating provides marginal improvements in uncertainty quantification. Both models remain vulnerable during rapid market changes, highlighting the trade-off between stability and responsiveness in sequential forecasting.

