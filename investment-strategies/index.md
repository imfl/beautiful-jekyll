---
layout: page
title: investment strategies
subtitle: to identify promising sectors
use-site-title: true
---

## A Sector Rotation Trading Strategy in Hong Kong Stock Market

We design and implement a sector rotation trading strategy in Hong Kong Stock Market.

Strategically, we rotate the focus of our investment from one industry sector to another, according to the fluctuations of the business cycle.

The core of our strategy is

1. to detect the stage of the cycle, and
2. to quantify the descriptive recommendations such as strong buy, neutral and sell.

We apply Principal Component Analysis in selecting the stocks, Hidden Markov Model (HMM) to detect the stage of the business cycle, and employ Monte Carlo methods, with Gibbs sampling ideas, for optimization.

We also discuss using statistical techniques, such as skewness, kurtosis, and variance ratio tests, for ﬁne-tuning our strategy.

### More Information 

This project is an academic project that I did together with Wei Jian and Xing Siyu, for [*MAFS 6010K Algorithmic Quantitative Finance*](http://cting.x10host.com/AQF/AQF.html), a master-level course that I took at the Math department at HKUST in Summer 2017.

This project was supervised by Prof. Christopher Ting from the Singapore Management University.

I am responsible for designing most of the algorithms, and for implmenting the HMM part using R (with `depmixS4` pacakge).

- For the R code for this project, click [here](https://github.com/imfl/investment-strategies) (GitHub).
