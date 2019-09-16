---
title: "Boosting 이란"
permalink: /study/ensembles/3/
comments: true
categories: [ML, Ensembles]
toc: true
---

**Reference**

- https://blog.statsbot.co/ensemble-learning-d1dcd548e936
<br><br>

## Boosting

- boosting은 week learners를 조합하여 strong learners로 만들어 나가는 알고리즘이다.
  - week learners : 상대적으로 성능이 떨어지는 learners
  - strong learners : 상대적으로 좋은 성능을 발휘하는 learners


## AdaBoost

![fig.2](../images/ensembles_3_2.png)

- Classifier 학습 과정
  - Input : $$ (x_1, y_1), \cdots ,(x_N, y_N) where y_i \in {-1, +1}, N : \sharp of samples $$
  1. 모든 데이터의 가중치 초기화
    - $$ w_i =
    \begin{cases}
    \cfrac{1}{M}, & \mbox{if }y_i = +1\mbox{(positive)} \\
    \cfrac{1}{L}, & \mbox{if }y_i = -1\mbox{(negative)}
    \end{cases} $$ <br>
    - $$ M : \sharp of positive samples $$ <br>
    - $$ L : \sharp of negative samples $$ <br>

  2. 학습 ($$ f_j(x) $$)
  3. 모델의 오류 계산 <br>
    - $$ \boldsymbol{\varepsilon}_j =
      \ cfrac{\sum\limits_{k=1}^{N} w_k}$$
  4. 모델의 가중치 계산
  5. 데이터의 가중치 계산
  6. 2-5 T번 반복

## XGBoost

## LightGBM
