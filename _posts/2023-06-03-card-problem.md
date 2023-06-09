---
layout: single
title: "영화-\"네이든\"-카드문제"
categories: mathematics
tag: [mathematics, computer-science]
---

이산수학을 활용하여 풀 수 있는 간단한 문제다.

내용은 다음과 같다.

- 무작위로 선택된 20장의 카드를 뒷면이 보이게 일렬로 놓는다.
- 뒷면이 보이는 카드 중 하나를 골라 뒤집고, 그 카드 바로 오른쪽에 있는 카드도 뒤집는다.
    - 단, 오른쪽 맨 끝의 카드를 고를 때에는 그 카드만 뒤집는다.
- 뒷면이 보이는 카드가 남아 있는 동안 고르고 뒤집기를 거듭 반복한다.
- 어떻게 카드를 고르든지 결국에는 모든 카드가 전부 앞면이 됨을 증명하라.

하지만 여기선 20장이 아니라, n장으로 일반화해서 풀이할 것이다.

예를 들어, 다음과 같이 주어졌다고 가정하자.

◇◆◇◆◇◆

(◇가 앞면, ◆가 뒷면이다.)

오른쪽부터 첫 번째라고 하면, 첫 번째 카드를 뒤집으면

◇◆◇◆◇◇가 된다. 그리고 다섯 번째 카드를 뒤집으면

◇◇◆◆◇◇가 된다. 여기서 네 번째 카드를 뒤집으면

◇◇◇◇◇◇가 되고, 이제 더 이상 뒤집을 수 있는 카드가 없으므로, 정지한다.

# 증명

◇(앞면)을 0

◆(뒷면)을 1
이라고 하자.

그럼 카드 문제는 이제 이진수로 이루어진 이진수에 대한 문제로 바뀐다.

즉, "어떤 카드를 선택하든, 항상 유한한 선택을 통해 0이 되느냐"인 감소 수열에 대한 문제로 바뀐다.

3가지 케이스만 고려하면 된다.

1. 오른쪽 카드가 뒷면인 경우
    - ...11...인 경우 ...00...이 되므로, ...11... > ...00...이다. 따라서 감소한다.
2. 오른쪽 카드가 앞면인 경우
    - ...10...인 경우 ...01...이 되므로, ...10... > ...01...이다. 따라서 감소한다.
3. 첫 번째 카드를 고른 경우
    - ...1인 경우 ...0이 되므로, ...1 > ...0이다. 따라서 감소한다.

즉, 어떠한 방식으로 선택을 하든 감소하므로, 유한한 선택으로 항상 0이 됨을 알 수 있다. ■