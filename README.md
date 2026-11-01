# Reliance Industries Stock Direction Prediction

A machine learning study that evaluates whether historical market data can help classify Reliance Industries Ltd. (NSE: RELIANCE) stock returns over the next five trading sessions as **down**, **flat**, or **up**.

This is an educational model evaluation project, not investment advice or a trading strategy.

## Project Overview

The project compares three classifiers:

- Majority-class baseline
- Logistic Regression
- Random Forest

Models use chronological data splits to evaluate performance on later periods. The target is based on the stock’s return over the next five trading sessions. Returns below **−1.318%** are labeled down, returns between **−1.318% and +1.318%** are labeled flat, and returns above **+1.318%** are labeled up.

## Data and Features

The presentation describes daily Reliance market data sourced through `yfinance`. Features include:

- Historical returns over several lookback periods
- Rolling volatility
- Daily high-to-low range
- Closing-price position within the daily range
- Relative trading volume

The target is the five-session forward return category.

> Add the exact data period, data retrieval steps, and any source files or scripts here.

## Models and Evaluation

The models are evaluated with:

- Accuracy
- Balanced accuracy
- Macro F1 score
- Confusion matrices

In the reported validation comparison, Logistic Regression had the strongest average scores among the evaluated models. On the reported final test set, it achieved:

| Metric | Logistic Regression |
|---|---:|
| Accuracy | 0.363 |
| Balanced accuracy | 0.351 |
| Macro F1 | 0.320 |

Performance was modest. Many down and up observations were classified as flat, so overall accuracy alone does not capture how well the model identifies each direction.

## Limitations

- Results depend on the chosen ±1.318% flat-class threshold.
- The listed features do not capture every influence on stock prices, such as news and company events.
- Market behavior can change over time.
- Historical results do not guarantee future performance.
- A backtest should account for transaction costs, slippage, taxes, execution timing, and other trading constraints before drawing economic conclusions.

## Repository Contents

_Add the files that are actually included in this repository, for example:_

- `notebooks/` — analysis notebooks
- `src/` — data preparation and modeling code
- `data/` — datasets or instructions for obtaining them
- `reports/` — charts and presentation
- `requirements.txt` — Python dependencies

## Setup

```bash
git clone <repository-url>
cd reliance-stock-direction-ml
python -m venv .venv
