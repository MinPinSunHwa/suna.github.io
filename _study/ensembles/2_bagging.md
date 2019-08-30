---
title: "Bagging"
permalink: /study/ensembles/2/
comments: true
categories: [ML, Ensembles]
toc: true
---

**Reference**

- https://blog.statsbot.co/ensemble-learning-d1dcd548e936
- https://ko.wikipedia.org/wiki/%EB%9E%9C%EB%8D%A4_%ED%8F%AC%EB%A0%88%EC%8A%A4%ED%8A%B8
<br><br>

## 1. Bagging

- Bagging은 bootstrap의 집계를 의미한다.
  - bootstrap은 random sampling하여 만든 훈련 데이터셋의 서브셋이다.
<br><br>

- Bagging의 한 가지 방법으로 estimate의 분산을 줄이기 위해 여러 estimate의 평균을 구하는 방법이 있다.
  - $$ f(x) = \cfrac{1}{M} \sum_{m=1}^{M} f_m(x) $$ <br>
  - 각 base learners 결과값을 집계하는데, 다음과 같이 집계한다.
    - classification의 경우, voting
    - regression의 경우, 평균
<br><br>

## 2. Random Forest

![fig.1](../images/ensembles_2_1.png)

- 주로 사용하는 bagging 모델로 Random Forest가 있다.
  - 각 bootstrap sample 별로 만들어진 decision tree 모델을 ensembles 한 것이다.
  - 랜덤성에 의해 tree들이 서로 조금씩 다르게 만들어 진다.
  - 모든 feature를 사용하는 대신 random으로 feature를 선택하면, tree를 좀더 random으로 만들 수 있다.
  - forest의 bias가 약간 증가하지만, 여러 tree의 평균 연산으로 노이즈에 대한 민감함이 감소했기때문에 variance는 감소된다.
