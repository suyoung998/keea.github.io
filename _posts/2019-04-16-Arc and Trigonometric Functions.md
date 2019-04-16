---
layout: post
title:  3D그래픽 프로그래밍 02
category: 3D Graphics Programming
description: Arc and Trigonometric Functions
---
# Arc and Trigonometric Functions
[동영상 강의 : # LinearAlgebra03 Arc and Trigonometric Functions](https://youtu.be/JYOOUPPB1w8)

<div class="youtube">
<iframe src="https://www.youtube.com/embed/JYOOUPPB1w8?list=PLrrTotxaO6khHInVhLSw3X16VucWW1v1Y" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

## 용어 정의

### 선

- 직선(line) : 선에 대해서 양끝점이 정해지지 않은 선.

- 레이(광선, 반직선, ray) : 직선의 한쪽 끝점이 정해진 선.

- 라인 조각(line segment) : 양 끝점이 모두 정해진 선.

  ![그림1](https://user-images.githubusercontent.com/26755686/56167831-3bc6af80-6014-11e9-9da0-c9b2aefac086.png)

  라인 세그먼트의 경우 양 끝점을 begin, end로 표시할 수 있음.

  레이의 경우 시작하는 끝점을 테이(tail)이라고 하고, 광선이 진행하는 방향의 끝점을 헤드(head)라고 함.

  ![그림2](https://user-images.githubusercontent.com/26755686/56167977-babbe800-6014-11e9-984d-97a73386c03f.png)

### 원

![그림3](https://user-images.githubusercontent.com/26755686/56168871-6403dd80-6017-11e9-9d22-96e97478b734.png)

- 원 : 한 점에서 똑같은 거리를 가진 모든 점의 집합.

- O : 원의 중심.

- 지름(diameter) : 원의 중심 O를 지나는 직선을 그었을 때 원의 양점과 만나는 라인 세그먼트의 거리.

- 반지름(radius) : 지름의 절반.

- 부채꼴(sector) : 중심이 O, 반지름의 길이가 r인 원에서, 두 반지름 OP, OQ를 그을 때, 이 두 반지름과 두 점 P, Q가 정하는 호로 이루어지는 도형.

- 활꼴 (circular segment) : 원주 위의 서로 다른 두 점이 만드는 호와 현으로 이루어진 도형.

- 호(arc) : 원주상에서 두 점 사이의 부분.

### 좌표계

![그림1](https://user-images.githubusercontent.com/26755686/56175373-f31def00-6031-11e9-9321-746d8d8c4df1.png)

2차원과 3차원 축 : 위의 3차원 축은 일반적으로 많이 사용되는 오른손 좌표계(right-hand coordinatesystem).

오른손 좌표계 : OpenGL, 3D Max 프로그램 등 사용. 열 벡터로 표현.

왼손 좌표계 : DirectX 프로그램 등 사용.

## 기본개념
### 라디안

반지름의 길이가 r인 원 위에서 길이가 r인 호를 잡을 때, 이 호에 대한 중심각의 크기는 반지름의 길이 r에 관계 없이 일정. 이때 이 크기를 단위로 하여 일반 각의 크기를 측정하는 방법을 **호도법**이라하고 이 단위를 **라디안**(radian)이라고 함.

![그림2](https://user-images.githubusercontent.com/26755686/56175967-658fce80-6034-11e9-9e07-5038e23fd16a.png)



라디안 : 반지름이 r인 원에서, 원호의 길이가 r일 때 원의 중심과 원소가 이루는 비율을 1라디안. 반원의 길이는 pi로 정의하며, 근사값은 3.141592

> pi 라디안(radian) = 180도(degree)

![그림3](https://user-images.githubusercontent.com/26755686/56177488-c79f0280-6039-11e9-8cc4-f9c523027bd1.png)

단위 원(unit circle): 반지름의 길이가 1인 원.


$$
cos(\theta) = |\overline{OPx}|
$$

$$
sin(\theta) = |\overline{OPy}|
$$



#### 직각 삼각형

![그림4](https://user-images.githubusercontent.com/26755686/56178126-0a61da00-603c-11e9-80be-46b47bbb7e3d.png)
$$
sin(\theta) = \dfrac{b}{c}
$$

$$
cos(\theta) = \dfrac{a}{c}
$$

$$
tan(\theta) = \dfrac{b}{a}
$$

피타고라스 정리
$$
c^2 = a^2 + b^2, c = \sqrt{a^2+b^2}
$$
c가 1이라면
$$
1^2 = (cos\theta)^2 + (sin\theta)^2, 1 = sin^2\theta + cos^2\theta
$$
이러한 비율을 구하는 함수를 **삼각함수(trigonometrix function)**

C 표준 라이브러리는 sine, cosine을 구하는 표준 삼각함수를 제공.

- sin()
- cos()

역 함수

- asin()
- acos()