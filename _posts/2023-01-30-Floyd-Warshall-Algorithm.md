---
layout: post
title: 플로이드-와샬 알고리즘(Floyd-Warshall Algorithm)
subheading: Floyd-Warshall Algorithm
author: Pacho
categories: algorithm
tags: algorithm Floyd-Warshall graph DP DynamicProgramming
sidebar: []
---

## 개요
해당 알고리즘은 그래프 이론에서 착안된 이론 중 하나로써 반의 가중치가 양수 뿐만 아니라 음수인 경우의 가중치를 가지는 이동 경로에서도 사용할 수 있어 이를 통해 최단 경로를 찾는 알고리즘이다.

플로이드-와샬 알고리즘 자체는 경로를 반환하지 않지만 약간의 수정 작업을 거친다면 경로까지 반환할 수 있는 알고리즘을 만들 수 있다.

## 시간 복잡도
해당 알고리즘 같은 경우는 각 꼭지점 쌍을 지나는 그래프의 모든 경로를 비교하기 때문에 3개의 중첩 for문이 사용된다. -> 이 때문에 시간복잡도가 O(n^3)이다.

​

## 사용 방법
기본적으로 ShortPath{최단거리}(I, J, 0) = w(i, j) 이고,

이를 재귀적으로 이용할 경우,

ShortPath(i,. J, k) = mininum(ShortPath(i, J, k - 1), ShortPath(i, k, k - 1) + ShortPath(k, J, k - 1))

가 된다.

플로이드-와샬 알고리즘은 다른 알고리즘과 달리 거의 대부분이나 모든 꼭짓점 쌍의 변으로 연결된 밀집 그래프에서 경로를 계산할 때 적합하다. -> 아마 섬이 존재하는 그래프는 안되는 듯?

또한, 가중치에 음수가 없는 경우에는 플로이드-와샬 보다는 다익스트라 알고리즘이 적합하다. (why? 시간복잡도가 낮아서)

해당 알고리즘을 이용한 문제는
https://www.acmicpc.net/problem/11404