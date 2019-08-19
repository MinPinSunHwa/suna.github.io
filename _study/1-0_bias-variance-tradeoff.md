---
title: "Bias Variance TradeOff"
permalink: /study/ensembles/0/
comments: true
categories: [ML]
toc: true
---

**Reference**
- http://scott.fortmann-roe.com/docs/BiasVariance.html

- http://www.machinelearningtutorial.net/2017/01/26/the-bias-variance-tradeoff/


## 1. Bias and Variance

$$ Err(x) = E[(Y - \hat{f}\left(x\right))^2] $$
$$ Err(x) = (E[\hat{f}\left(x\right)] - f\left(x\right))^2 + E[(\hat{f}\left(x\right))] $$
