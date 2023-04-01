---
title: "Kalman Filters From Scratch"
publishDate: "2022-09-03T00:00:00Z"

authors:
- admin

categories:
- Finance
- Programming

tags:
- Markets
- Machine Learning

summary: Time Series analysis using stock market data and machine learning.

featured: true
reading_time: true
draft: true

markup: mmark


image:
  placement: 2
  preview_only: false
---

In these post, I will be focusing on applying various time series analysis methods for stock market data utilizing Kalman Filters.

## What are Kalman Filters?

A Kalman Filter is a state-space model applied to linear dynamic systems; systems whose state is time-dependent and state variations are represented linearly. The model is used to estimate unknown states of a variable based on a series of past values. The procedure is two-fold: a prediction (estimate) is made by the filter of the current state of a variable and the uncertainty of the estimate itself. When new data is available, these estimates are updated.

In Quant Finance, particularly trading, Kalman Filter is used to update hedging ratios between assets in a statistical arbitrage pairs trade. Generally, there are three types of inference that are of interest when considering state space models:

* Prediction: Forecasting subsequent values of the state
* Filtering: Estimating the current values of the state from past and current observations
* Smoothing: Estimating the past values of the state given the observations

