# ds_ - Junior Data Scientist Assignment: Trader Behavior Insights

## Overview

This repository contains the submission for the Web3 Trading Team's Data Science qualification assignment. The objective was to analyze the relationship between
high-frequency Hyperliquid trader behavior and overall Bitcoin Market Sentiment (Fear/Greed Index) to derive actionable, contrarian trading signals.

The core finding is documented in the final report: **The most profitable traders consistently act as contrarians, selling into market Greed and accumulating during market Fear.**

## Project Structure

The project strictly follows the required directory structure:

ds_/ ├── notebook_1.ipynb # Main analysis notebook (viewable via the Colab Link) 
     ├── csv_files/ │ └── merged_data.csv # Synchronized daily metrics merged with sentiment data.
     ├── outputs/ │
	├── pnl_by_sentiment.png # Chart 1: Aggregate Market PnL vs. Sentiment.
	│ └── smart_money_bias.png # Chart 2: Smart Money (Top 10%) Buy/Sell Bias.
     ├── ds_report.pdf # Final report summarizing key insights and strategy. 
	└── README.md # This file.

## How to View and Reproduce the Analysis

The complete, executed code is provided in the Google Colab environment for transparency and ease of review.

### 1. Code Environment

The entire analysis was performed in a single Google Colab notebook:

* **Google Colab Link:** [https://colab.research.google.com/drive/1Ju0aPoi0wMKNsjQLG7QFh2y_DTQuGuMm?usp=sharing]

### 2. Required Data

The raw datasets (`historical_data.csv` and `fear_greed_index.csv`) were provided as Google Drive links in the assignment instructions 
and were uploaded directly to the Colab session environment.

### 3. Execution Steps

The notebook is divided into four main cells:

1.  **Setup & Loading:** Imports libraries and loads the two raw CSV files.
2.  **Cleaning & Merging:** Converts timestamps, aggregates high-frequency data to a daily level, and performs an **inner merge** to synchronize 
trade activity with market sentiment, producing `merged_data.csv`.
 *(Note: Due to a data temporal mismatch, the final merged dataset is limited to approximately 6-7 overlapping days.)*
3.  **Aggregate Analysis:** Calculates and visualizes the collective market performance by sentiment (`pnl_by_sentiment.png`).
4.  **Smart Money Signal:** Identifies the Top 10% of profitable accounts and analyzes their net trading bias across sentiment periods, generating the crucial 
**contrarian signal** (`smart_money_bias.png`).