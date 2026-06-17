Machine Learning-Based Quantitative Trading Strategy Framework

A Python-based quantitative research and machine learning framework for analyzing historical NIFTY 50 index data, backtesting systematic trading strategies, and dynamically selecting trading approaches using market regime classification.

Overview

This project combines traditional quantitative finance techniques with machine learning to evaluate and improve trading decisions on the NIFTY 50 index.

The framework consists of two major components:

Quantitative Strategy Research & Backtesting
Momentum Strategy
Moving Average Crossover Strategy
Buy-and-Hold Benchmark
Machine Learning-Based Strategy Selection
Market Regime Classification
Dynamic Strategy Recommendation
Random Forest-Based Prediction Engine

The objective is to identify favorable market conditions and adapt trading strategies accordingly while evaluating performance through industry-standard risk and return metrics.

Features
Quantitative Research Framework
Historical NIFTY 50 data analysis
Data cleaning and preprocessing
Feature engineering using technical indicators
Momentum strategy development
50-Day / 200-Day Moving Average crossover strategy
Buy-and-Hold benchmark comparison
Backtesting Engine
Daily return calculation
Strategy return simulation
Equity curve generation
Benchmark comparison
Performance Evaluation
Compound Annual Growth Rate (CAGR)
Sharpe Ratio
Maximum Drawdown
Win Rate
Cumulative Return Analysis
Machine Learning Module
Market regime classification
Bull, Bear, and Sideways market detection
Random Forest Classifier
Feature importance analysis
Dynamic strategy recommendation engine
Dataset

The project uses historical NIFTY 50 index data containing:

Column	Description
Date	Trading Date
Open	Opening Price
High	Highest Price
Low	Lowest Price
Close	Closing Price
Shares Traded	Daily Trading Volume
Turnover	Daily Market Turnover

Period Covered:

01-Apr-2024 to 31-Mar-2025
Technical Indicators Used
Trend Indicators
20-Day Simple Moving Average (SMA20)
50-Day Simple Moving Average (SMA50)
200-Day Simple Moving Average (SMA200)
Momentum Indicators
5-Day Returns
10-Day Returns
20-Day Returns
Volatility Indicators
20-Day Rolling Volatility
Relative Position Indicators
Trend Strength
Price vs SMA50
Strategy 1: Momentum Trading

The strategy enters a long position when momentum remains positive.

Formula:

Momentum_20 = Close / Close.shift(20) - 1

Trading Rule:

Momentum > 0  → Long
Momentum ≤ 0  → No Position
Strategy 2: Moving Average Crossover

The strategy identifies trend changes using moving averages.

Trading Rule:

SMA50 > SMA200  → Long
SMA50 ≤ SMA200 → No Position

This is commonly known as the Golden Cross / Death Cross framework.

Machine Learning Market Regime Classification

The machine learning component predicts future market conditions.

Market Regimes
Class	Market Condition
0	Bear Market
1	Sideways Market
2	Bull Market
Label Generation

Future 5-day returns are used to create market labels.

Future Return > 2%      → Bull
Future Return < -2%     → Bear
Otherwise               → Sideways
Model
Random Forest Classifier

Parameters:

n_estimators = 300
max_depth = 6
min_samples_leaf = 5
Dynamic Strategy Recommendation

Based on the predicted market regime, the framework recommends a trading approach.

Predicted Regime	Recommended Strategy
Bull	Buy & Hold
Sideways	Momentum
Bear	Cash / No Exposure
Performance Metrics

The framework evaluates both trading strategies and machine learning recommendations using:

CAGR

Measures annualized portfolio growth.

Sharpe Ratio

Measures risk-adjusted return.

Maximum Drawdown

Measures worst portfolio decline from peak value.

Win Rate

Percentage of profitable trading periods.
