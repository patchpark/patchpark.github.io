---
title: 기계학습 Gradient Descent
date: 2024-03-18 01:00:00 +09:00
categories: [cs, 기계 학습]
---


글을 읽기 전 [Linear Regression](https://patchpark.github.io/posts/linearRegression)을 보고 오면 좋습니다.

# 직선 찾기
f(x) = wx + b 에서 우리가 찾아야 할 것은 w와 b이다. 찾아야 할 것이 2개임으로 최소 2개의 식이 필요하다.

중학교에서 배웠던 연립방정식을 생각해보면 w와 b를 구하기 위해서는 2개의 좌표만 있으면 풀 수 있었다. 하지만 최소 2개의 식이 필요한 이유는 무엇일까?


![ML_06](https://github.com/patchpark/patchpark.github.io/assets/116805893/b28ed12e-a21e-4379-8c87-e82164295111)

위의 예시에서 볼 수 있듯이, 기존 연립방정식을 위해 주어진 좌표들은 정확한 직선 하나에 위치한 반면, 현실의 데이터들은 노이즈들이 존재하기에 2개의 좌표를 이었을 때 각각 다른 직선이 그려지는 것을 확인 할 수 있다. 그렇기에, 좌표가 많으면 많을수록 정확도가 올라간다.

그렇다면 직선을 어떻게 구할 수 있을까?


![ML_07](https://github.com/patchpark/patchpark.github.io/assets/116805893/0faa501e-0e5b-4c92-aa28-d78b3aab9291)

위의 그림에서 하이라이트로 표시된 부분의 합이 최소가 되도록 하는 w와 b값을 구하면 직선이 구해진다. 이를 식으로 표현 하면 (y-f(x))²로 나타 낼 수 있다.

![ML_08](https://github.com/patchpark/patchpark.github.io/assets/116805893/1586bce8-b692-4a69-a02d-5dc8e03ef5a7)

위의 그림에서 설명했듯이 미분하여 0이 되는 지점을 찾으면 Loss(w,b)가 최소가 되게 하는 w와 b를 구할 수 있을 것이다. 하지만 그것이 항상 가능한가라고 물어본다면 그렇지 않다. 

수많은 그래프 중 우리가 개형을 알고 있는 그래프는 매우 제한적이다. 그렇기에 복잡한 함수에서는 위의 방법을 쓸 수 없다. 예를 들어 y= w1⁵x + w2⁴x + b, y = e^wx + b 같은 함수들은 여전히 선형 회귀이지만, w와 b에 대한 미분이 복잡함을 확인 할 수 있다.

# Gradient Descent
그렇기에 등장한 방법이 Gradient Descent(경사하강법)이다.

![ML_09](https://github.com/patchpark/patchpark.github.io/assets/116805893/c21baaac-e7d3-4dfb-9724-474ba6656645)

위의 그림과 같이 Loss가 최소가 되는 값을 기준으로 왼쪽에서는 기울기가 음수, 오른쪽에서는 기울기가 양수임을 확인 할 수 있다. 그럼으로 어느 점에서의 기울기가 음수라면 오른쪽(양수)으로 이동, 양수라면 왼쪽(음수)으로 이동해야 최솟값에 다다를 수 있음을 알 수 있다. 따라서 다음과 같은 식을 통해 최솟값을 구할 수 있다.

![ML_10](https://github.com/patchpark/patchpark.github.io/assets/116805893/6bd15282-c3ab-4dc7-ba98-c36ff66fd95c)

# Gradient Descent의 주의점과 한계점

### 주의점
이동 정도를 결정하는 rw를 너무 적거나 크게 설정하면 문제가 발생한다. rw가 너무 적다면, 최솟값에 도달하기까지 걸리는 시간이 너무 오래 걸리며, rw가 너무 크다면 최솟값에 수렴하지 못하고 오히려 발산 할 수가 있다.


![ML_11](https://github.com/patchpark/patchpark.github.io/assets/116805893/38b9dcf7-f648-4184-846d-e15e2d566682)


### 한계점

Loss를 미분한 값이 0인 지점을 찾으면 종료됨으로, 그 값이 함수 전체에서의 최솟값인지 일정 지역내에서만의 최솟값인지 알 수가 없다. 이러한 한계점은 현재로서는 해결할 수 없는 문제이다. 아래는 그러한 예시이다.

![ML_12](https://github.com/patchpark/patchpark.github.io/assets/116805893/223fea11-91e2-476c-bd00-a5641ce1ceb3)
