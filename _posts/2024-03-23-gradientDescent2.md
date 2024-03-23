---
title: 기계학습 Gradient Descent(2)
date: 2024-03-23 22:00:00 +09:00
categories: [cs, 기계 학습]
---


글을 읽기 전 [Gradient Descent(1)](https://patchpark.github.io/posts/gradientDescent1)을 보고 오면 좋습니다.

# Gradient Descent의 확장
[Gradient Descent(1)](https://patchpark.github.io/posts/gradientDescent1)에서 우리는 single linear에 대한 Gradient Descent를 알아 보았다. 그러면 Gradient Descent를 multivariate linear에 대해서 어떻게 확장 해야 할까?


![GD_01](https://github.com/patchpark/patchpark.github.io/assets/116805893/08ffc9f5-0c58-436a-b1ac-042f48bacd4f)

이전의 포스팅에서 우리는 w와 b에 대한 미분을 각각 따로 생각하여 그래프에서 최솟값을 찾는다 생각했지만 사실은 3차원에서 최솟값을 찾는 작업이다.


![GD_02](https://github.com/patchpark/patchpark.github.io/assets/116805893/db0d6ec3-b58e-441e-ae20-e7c4242ee45e)

즉 linear regression이 변수 여러개를 갖는다 하더라도, 우리가 N차원을 생각하지 못할 뿐 여러 기울기들에 의해 최솟값을 찾아간다는 사실은 변함이 없음으로 다음과 같이 확장 할 수 있다.

![GD_03](https://github.com/patchpark/patchpark.github.io/assets/116805893/d2c5f23d-5230-4785-a40c-7f4785e8cdbb)

# Stochastic Gradient Descent
머신 러닝을 위한 데이터 셋은 굉장히 많다. Gradient Descent를 이용하게 되면, 데이터 셋만큼 미분후 더하는 작업을 해주어야한다. 이러한 과정은 메모리적 측면에서도, 계산적인 측면에서도 굉장히 무겁고 컴퓨터에게 부담을 주게 된다. 그래서 등장하게 된 것이 SGD(Stochastic Gradient Descent) 기법이다. 

SGD란 전체 데이터 셋을 일정 크기로 잘라(mini-batch), 각각의 배치에서 GD를 수행하는 기법이다.

예를 들어, 100만개 데이터 셋에 대해 GD를 하기에는 너무 오래 걸리기 때문에 이를 256개의 배치로 나눠 순차적으로 GD를 실행해 주는 것이다. 초기에는 방향성을 잡는 부분에 있어 GD와 별 차이가 없지만, 학습이 완료에 가까워지면 GD는 최솟값에 수렴하는 것과 달리, SGD는 최솟값 주변을 맴돌게 됨으로 GD와는 다르게 rw값의 수정이 필수적으로 요구된다.

![GD_04](https://github.com/patchpark/patchpark.github.io/assets/116805893/3bc91b57-907f-44da-aa84-3048e03427da)
