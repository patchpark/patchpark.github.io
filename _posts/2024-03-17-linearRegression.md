---
title: Linear Regression[java]
date: 2024-03-17 18:00:00 +09:00
categories: [cs, 기계 학습]
---

# 수학적 접근의 필요성

컴퓨터가 어떠한 그림을 입력 받으면, 컴퓨터는 그림을 숫자의 형태로 처리해 인식하게 된다. 예를 들어, 가로와 세로가 각각 50px로 이루어진 그림이 있다고 가정하면, 각각에 픽셀은 RGB 값으로 나타낼 수 있기 때문에, 컴퓨터는 그림을 50 x 50 x 3 = 7500개의 숫자로 인식할 것이다. 우리가 만약 7500차원의 표를 그릴 수 있다면, 그려진 그림을 보고 사물을 인식할 수 있을 것이다. 그러나 그 것을 그리거나 인식할 수 없기에 수학적 접근이 필요한 것이다.

# Linear Regression

Linear Regression에 대해 알아보기 위해 Linear와 Regression이 각각 무엇인지 알아보면

## Regression

지도 학습의 알고리즘 중 하나로서, 한국말로 번역하면 회귀라는 뜻이다. 또다른 지도 학습의 알고리즘으로는 Classification(분류)이 있다.

분류라는 명확한 단어에서 알 수 있 듯, Classification은 데이터들의 클래스를 두개로 구분하는 목적을 가지는 알고리즘이다.

Regression은 데이터들의 패턴을 찾는데 목적을 가지는 알고리즘이다.

예를 들어, 강아지인지 개인지를 판별하기 위해서는 Classification을, 부모의 키와 자식의 키 사이의 상관관계에 대한 예측을 하기 위해서는 Regression을 사용해야 한다.


![ML_03](https://github.com/patchpark/patchpark.github.io/assets/116805893/c9a6c604-8eff-48ee-88d8-5dad045bb5ed)


## Linear
Linear을 찾아보면 선(line)의 형용사 형태로, 선형이라는 뜻이다.

Linear Method란 입력 x가 결과 y를 도출하는데 있어서 기울기 w와 y절편 b만의 영향을 받는 f(x) = wx + b 형태의 함수이다.

즉, Linear Regression이란 데이터들의 경향성이 선형의 관계를 이루는 것이다.

![ML_04](https://github.com/patchpark/patchpark.github.io/assets/116805893/45171ea2-9e61-4789-8b45-786ced7ed13f)


## Linear Regression 의 종류
Linear Regression은 크게 single linear regression과 multivariate linear regression으로 나뉜다. single linear의 경우에는 변수가 하나여서 f(x) = wx + b 형태로 나타낼 수 있음을 생각하기 어렵지 않다. 그렇다면 multivariate linear regression은 어떨까?

이해 하기 쉽게 예를 들어보자면 어떤 서점의 총 수입은 온라인(컴퓨터)를 통한 판매, 핸드폰을 통한 판매, 매장 판매, 광고료 네가지의 합이라고 생각해자. 그렇다면 이러한 식을 생각할 수 있을 것이다.

![ML_05](https://github.com/patchpark/patchpark.github.io/assets/116805893/6c3e8b98-7a3a-4237-860b-5e23cdc9a5de)