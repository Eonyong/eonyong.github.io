---
layout: post
title: 퀵소트(Quick Sort) 정리
subheading: Quick Sort
author: Pacho
categories: algorithm
banner:
  video: 
  loop: true
  volume: 0.8
  start_at: 8.5
  image: 
  opacity: 0.618
  background: "#000"
  height: "100vh"
  min_height: "38vh"
  heading_style: "font-size: 4.25em; font-weight: bold; text-decoration: underline"
  subheading_style: "color: gold"
tags: algorithm sort quicksort
sidebar: []
---

## section 1
{% highlight ruby %}
개요
{% endhighlight %}
다른 원소와의 비교만으로 정렬을 수행하는 비교 정렬

## section 2
{% highlight ruby %}
시간복잡도
{% endhighlight %}
평균적으로는 O(N logN)이고 최악의 경우에는 O(N^2)이다.
최악의 경우는 정렬하고자하는 배열이 오름차순 혹은 내림차순으로 되어있는 경우이다.
매 단계에서 적어도 1 개의 원소가 자기자리를 찾게 됨
때문에 일반적으로 다른 O(N logN) 알고리즘 비해 훨씬 빠르게 동작

## section 2
{% highlight ruby %}
공간복잡도
{% endhighlight %}
메모리 측면에서도 O(logN)만큼의 메모리 차지
이는 제귀적으로 호출하기 때문에 최악의 경우에는 O(N)의 공간 복잡도로 보임

## section 2
{% highlight ruby %}
알고리즘
{% endhighlight %}
분할 정복을 통해 리스트를 정렬
리스트 가운데 하나의 원소를 선택하고 이를 피벗(p)이라 부른다.
피벗 앞에는 피벗보다 값이 작은 모든 원소들이 오고, 피벗 뒤에는 피벗보다 큰 모든 원소들이 오도록 둘을 나눈다. 이렇게 둘로 나누는 것을 분할이라고함.
분할된 두 개의 작은 리스트에 대해 재귀적으로 과정을 반복 -> 리스트 크기가 0이나 1이 될 때까지 진행

## section 2
{% highlight ruby %}
장점
{% endhighlight %}
불필요한 데이터의 이동을 줄이고 먼 거리의 데이터를 교환할 뿐만 아니라, 한 번 결정된 피벗들을 추후 연산에서 제외되는 특성을 가지므로 다른 정렬 알고리즘과 비교해도 현저히 빠르다.
정렬하고자 하는 배열 내부에서 교환(swap)이 이루어지다보니, 다른 메모리 공간을 차지하지 않는다.

## section 2
{% highlight ruby %}
단점
{% endhighlight %}
불안정 정렬
정렬되어 있는 배열에 대해서는 최악의 시간복잡도를 가진다.
 
## section 2
출처

https://gyoogle.dev/blog/algorithm/Quick%20Sort.html
https://ko.wikipedia.org/wiki/%ED%80%B5_%EC%A0%95%EB%A0%AC