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
    - $$ y_i \in \{-1, +1\} $$ <br>
    - $$ N $$ : sample 수

  - 모든 데이터의 가중치 초기화 $$ \cdots(1) $$
    - i번째 데이터의 가중치 $$ w_i $$ 초기화
    - $$ w_i^{(1)} =
      \begin{cases}
      \frac{1}{M}, & \mbox{if }y_i=+1\mbox{(positive)} \\
      \frac{1}{L}, & \mbox{if }y_i=-1\mbox{(negative)}
      \end{cases} $$ <br>
    - $$ M $$ : positive sample의 수
    - $$ L $$ : negative sample의 수

  - 학습(모델 생성) $$ \cdots(2) $$
    - t번째 모델 $$ \hat{f_t}(x) $$

  - 모델의 오류 계산 $$ \cdots(3) $$
    - t번째 모델의 오류 $$ \boldsymbol{\varepsilon}_t $$ 계산
    - $$ \boldsymbol{\varepsilon}_t =
      \cfrac{\sum\limits_{\underset{\hat{f_t}(x_k)\ne y_k}{k=1}}^{N} w_k}
      {\sum\limits_{k=1}^{N} w_k} =
      \cfrac{\text{오류인 데이터의 가중치 합}}{\text{전체 학습 데이터의 가중치 합}} $$ <br>

  - 모델의 가중치 계산 $$ \cdots(4) $$
    - t번째 모델의 가중치 $$ \alpha_t $$ 계산
    - $$ \alpha_t = \cfrac{1}{2}
      \ln \cfrac{1-\boldsymbol{\varepsilon}_t}{\boldsymbol{\varepsilon}_t} $$ <br>

  - 데이터의 가중치 계산 및 업데이트 $$ \cdots(5) $$
    - i번째 데이터의 가중치 $$ w_i $$ 업데이트
    - $$ w_i^{(t+1)} \leftarrow
      \begin{cases}
      \cfrac{w_i^{(t)} e^{-\alpha_t}}{W}, & \mbox{if }\hat{f_t}(x_k)=y_k\ (\text{예측이 맞은 경우}) \\
      \cfrac{w_i^{(t)} e^{\alpha_t}}{W}, & \mbox{if }\hat{f_t}(x_k)\ne y_k\ (\text{예측이 틀린 경우})
      \end{cases} $$ <br>
    - $$ W = \sum\limits_{k=1}^{N} w_k^{(t)} $$ <br>

  - $$ (2)- (5) $$ 과정 $$ T $$번 반복

## XGBoost

## LightGBM
