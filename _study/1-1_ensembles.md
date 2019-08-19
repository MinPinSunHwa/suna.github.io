---
title: "Ensemble 이란"
permalink: /study/ensenbles/1/
comments: true
categories: [ML]
toc: true
---

**Reference**

- https://blog.statsbot.co/ensemble-learning-d1dcd548e936
<br><br>

## Ensembles

- 여러 머신러닝 기법을 하나의 예측 모델로 결합하는 메타 알고리즘이다.
  - **Variance** 를 감소시키기 위해 *Bagging* 사용
  - **Bias** 를 감소시키기 위해 *Boosting* 사용
  - **predictions** 을 향상시키기 위해 *Stacking* 사용
<br><br>

- Sequential Ensembles
  - base learners가 순차적으로 생성된다(e.g. *AdaBoost*).
  - base learners 사이의 종속성을 이용한다.
  - 전체적인 성능은 이전에 틀리게 예측한 데이터에 더 높은 가중치를 부여하여 향상시킨다.
<br><br>

- Parallel Ensembles
  - base learners가 병렬로 생성된다(e.g. *Random Forest*).
  - 평균을 취함으로써 오류를 극단적으로 줄일 수 있기 때문에 base learners 사이의 독립성을 이용한다.
<br><br>

- 대부분의 Ensembles 기법은 같은 타입의 learners를 생성하여 Ensemble한다.
- 다른 타입의 learners를 생성하여 Ensemble하는 경우, base learners가 최대한 정확하고 다양해야 한다.
