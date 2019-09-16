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

- Binary Classifier 학습 과정
  - Input : $$ (x_1, y_1),\ \cdots\ ,(x_N, y_N) $$
    - $$ y_i \in {-1, +1} $$
    - $$ N $$ : sample 수

  - 모든 데이터의 가중치 초기화 $$ \cdots(1) $$
    - $$ w_i =
      \begin{cases}
      \cfrac{1}{M}, & \mbox{if }y_i=+1\mbox{(positive)} \\
      \cfrac{1}{L}, & \mbox{if }y_i=-1\mbox{(negative)}
      \end{cases} $$ <br>
    - $$ M $$ : positive sample의 수
    - $$ L $$ : negative sample의 수

  - 학습(모델 생성) $$ \cdots(2) $$
    - $$ \hat{f_j}(x) $$: j번째 모델

  - 모델의 오류 계산 $$ \cdots(3) $$
    - $$ \boldsymbol{\varepsilon}_j =
      \cfrac{\sum\limits_{\underset{\hat{f_j}(x_k)\ne y_k}k=1}^{N} w_k}
      {\sum\limits_{k=1}^{N} w_k}$$ <br>
    - $$ \boldsymbol{\varepsilon}_j $$ : j번째 모델의 오류

  - 모델의 가중치 계산 $$ \cdots(4) $$
    - $$ \alpha_j = \cfrac{1}{2}
      \ln \cfrac{1-\boldsymbol{\varepsilon}_j}{\boldsymbol{\varepsilon}_j} $$ <br>
    - $$ \alpha_j $$ : j번째 모델의 가중치

  - 데이터의 가중치 계산 $$ \cdots(5) $$
    - $$ w_i \leftarrow
      \begin{cases}
      \cfrac{w_i e^{-\alpha_j}}{\sum\limits_{k=1}^{N} w_k}, & \mbox{if }\hat{f_j}(x_k)=y_k \\
      \cfrac{w_i e^{\alpha_j}}{\sum\limits_{k=1}^{N} w_k}, & \mbox{if }\hat{f_j}(x_k)\ne y_k
      \end{cases} $$ <br>

  - $$ (2)- (5) T $$ 번 반복

## XGBoost

## LightGBM
