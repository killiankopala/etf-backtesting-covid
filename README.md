# Historical ETF Backtesting During the COVID-19 Market Shock

**UC Berkeley MIDS 200 | Fall 2025**  
*Team: Killian K. Carter*

---

## Overview

This project builds a Python backtesting framework to evaluate how rules-based trading strategies performed across major U.S. equity sectors during the COVID-19 market crash and recovery (2020–2021).

Using historical price data for six S&P 500 sector ETFs downloaded from Yahoo Finance, the framework applies a consistent signal-generation and portfolio evaluation pipeline to measure strategy performance under stress, throughout the rebound, and across the full COVID window.

---

## Strategies Evaluated

| Strategy | Type |
|---|---|
| Buy-and-Hold | Passive benchmark |
| 50-Day SMA | Trend-following |
| Buy-the-Dip | Mean-reversion |
| Multi-Factor Technical | Composite signal (RSI, MACD, momentum, volatility) |
| Regime Strategy | Market phase detection |
| SMA Crossover | Long-term trend signal |

---

## Market Segments

- **SPY** — Broad S&P 500
- **XLE** — Energy
- **XLF** — Financials
- **XLI** — Industrials
- **XLP** — Consumer Staples
- **XLV** — Healthcare

---

## Analysis Windows

Each strategy is evaluated across three market periods:

1. **Full COVID Period** — Jan 2020 to Dec 2021
2. **Crash Phase** — Feb 20 to Mar 23, 2020
3. **Recovery Phase** — Mar 23 to Nov 9, 2020

---

## Key Features

- Modular strategy functions — each strategy returns a boolean signal Series, cleanly separated from the backtesting engine
- Financial feature engineering: 20/50/200-day SMAs, daily and 5-day returns, 20/60-day volatility, volatility ratio, average volume, intraday range, gap
- Backtester class handles position sizing, return calculation, and performance metrics across all strategies and market segments
- Visualization pipeline for comparative strategy performance across regimes

---

## Tech Stack

- Python 3
- Pandas, NumPy, Matplotlib, Seaborn
- Google Colab

---

## Files

| File | Description |
|---|---|
| `Final_Project_Backtesting.ipynb` | Full analysis notebook |
| `Final_Project_Report.pdf` | Written report with findings and methodology |

---

## Key Findings

- Buy-and-Hold was the strongest overall performer, delivering the highest returns across multiple sectors
- Rules-based strategies showed significant sensitivity to the crash phase — most underperformed the passive benchmark during extreme volatility
- Recovery phase performance diverged sharply across sectors, with energy (XLE) showing the most strategy-dependent behavior
