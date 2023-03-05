---
layout: post
title: 작심삼일 JavaScript 정리 - 1
subheading: JavaScript
author: Pycho
categories: JavaScript
tags: JavaScript study
sidebar: []
---

**목차**
- [**JavaScript란?**](#javascript란)
- [**변수와 상수**](#변수와-상수)
- [**데이터 타입**](#데이터-타입)
- [**연산자**](#연산자)
- [**조건문**](#조건문)
- [**switch/case 문**](#switchcase-문)
- [**함수**](#함수)
- [**화살표 함수**](#화살표-함수)
- [**객체**](#객체)
- [**반복문**](#반복문)
- [**배열 내장함수**](#배열-내장함수)



이번 JavaScript 정리 공부가 작심삼일이 될 수 도 있지만 최대한 열심히 해보자는 의미에서 진행하는 정리 노트이다.



# **JavaScript란?**

	- 웹 브라우저에서 사용하기 위해 만들어진 프로그래밍 언어
	- 90년대부터 주로 웹 브라우저 상에서 UI를 동적으로 보여주기 위해 사용
	- 현재에 이르러서는 웝 브라우저에 국한되지 않고 node.js runtime 같은 툴을 통해 서버에서도 사용



# **변수와 상수**

	- 변수를 선언할 때, 하나의 태그 같은 걸 앞에 써주는 데 이걸 동태 병수인지 상수인지 구분을 한다.
	- 변수의 경우에는 예전부터 `let a = 1;` 처럼 사용할 변수명 앞에 표시를 해줬음.
	- let의 경우에는 선언이후에 값을 수정할 수 있어서 변수로 사용할 값에 붙여주고 중복 선언이 불가
	- var 라는 태그도 있는데 이것도 변수 앞에 붙여주는 데 중복 선언이 가능해서 최근 들어서는 var 사용을 지양하고 있음
	- 상수 선언에 있어서는 `const`를 붙여 원주율 같은 변하지 않는 값을 선언할 때 사용



# **데이터 타입**

  - 데이터 타입에는 숫자(number), 문자열(string), 참/거짓(boolean), 없음(null), 선언되지 않음(undefined)이 있다.



# **연산자**

  - **산술 연산자**: 사칙연산 기호로서 `+, -, *, /`가 있다. 또한 `a++와 ++a`같은 연산자도 있는데 이것도 산술 연산자의 일부이다. 여기서 `a++`는 어떠한 작업 이후에 +1, `++a`는 +1 이후에 어떠한 작업을 진행하는 것이다.
  - **대인 연산자**: 특정 값에 연산을 한 값을 바로 적용할 때 사용. `ex) a += 1, a -= 1, a *= 1, a /= 1`
  - **논리 연산자**: boolean type을 위한 연산자. 주로 조건문 if에 많이 사용된다. 종류로는 `!(not), &&(and), ||(or)`이 있다.
    - !(not): true -> false, false -> true 처럼 참/거짓을 반대로 말한다.
    - &&(and): 비교하는 두 값이 참이면 true, 아니면 false
    - ||(or): 비교하는 두 값이 거짓이면 false, 아니면 true
    - 논리 연산자도 연산 순서가 있는데, 괄호를 하지 않는다면 not -> and -> or 순으로 연산을 수행한다.
  - **비교 연산자**: 두 값을 비교하는 연산자로 JavaScript에서는 `==` 와 `===`, `!==` 와 `!=`가 있는데, 차이점으로는 `===`, `!==`는 type까지 비교하고 `==`, `!=`는 type을 비교하지 않고 값만 비교한다.



# **조건문**

  - "만약에 ~ 한다면 ~ 하자." 라는 구문을 생각하면 편한데, 표현으로는
  ```javascript
    if(조건문1) {
      do something;
    } else if (조건문2) {
      do something
    } ... {
      ...
    } else {
      do something
    }
  ```
  형태로 이루어져 있다.



# **switch/case 문**

  - 해당 문법은 비교값이 특정 조건과 같을 때, 작업을 수행하는 문법이다. 각 case에는 마지막에 `break;`를 작성해줘야한다. 구성은 아래와 같다.
  ```javascript
    switch(비교값) {
      case 조건1:
        do something;
        break;
      case 조건2:
        do something;
        break;
      case 조건3:
        do something;
        break;
      ...
      default:
        do something;
    }
  ```
  로 구성된다.
  마지막의 `default`의 경우에는 어떠한 case에도 부합하지 않는 경우에 실행하는 구문이다.



# **함수**

	- 함수는 특정 코드를 하나의 명령으로 실행할 수 있게 해주는 기능
	- 함수를 만들 때에는 `function`키워드를 사용하며, 어떤 값을 받아올지 정해주는 지 정하는 것을 파라미터(매개변수)라고 함
	- 함수 내부에서 `return` 키워드를 통해 함수의 결과물을 지정할 수 있음




# **화살표 함수**
	
	- 함수를 표현하는데 화살표 문법을 사용하는 것인데 `function` 대신 `=>`룰 사용해서 함수 구현을 진행한다.
```javascript

	function	add(a: int, b: int) {
		return a + b;
	}

	const add = (a: int, b: int) => a + b;
```
 위 두 함수는 동일하게 작용한다.



# **객체**

	- 우리가 변수 혹은 상수를 사용하게 될 때 하나의 이름에 여러 종류의 값을 넣을 수 있게 해줌. {} 안의 내용은 `key: value` 형태로 작성
```javascript
	
	const cat = {
		name: ‘고양이’,
		age: 1
	};
```



# **반복문**

	- 가장 기본적인 반복문으로 `for`가 있다. 구조로는
```javascript
	for (초기 구문; 조건 구문; 변화 구문;) {
		코드;
	}
```
이다.

	- 특정 조건이 참인 경우, loop를 도는 함수를 만들 때에는 `while`문을 이용하여 반복문을 작성한다. 구조는
```javascript
	while (특정 조건) {
		코드;
	}
```
이다.

	- 배열에 관해서 반복문을 실행하는 데 있어서는 `for…of` 구문을 사용할 수 있다. 구조는
```javascript
	for (let 원소 of 배열) {
		코드;
	}
```
이다.




# **배열 내장함수**
  - [foreach](#foreach)
  - [map](#map)

	- 배열을 다루는 다양한 내장함수가 존재하는 데 이를 알고 있으면 유용하게 사용할 수 있다.
	- 가장 쉬운 배열 내장함수인 `forEach` 이다. 기존의 `for`문을 대체 시킬 수 있음.

	## forEach
	```javascript
		const superheroes = ['아이언맨', '캡틴 아메리카', '토르', '닥터 스트레인지'];
		
		for (let i = 0; i < superheroes.length; i++) {
			console.log(superheroes[i]);
		}
	
		superheroes.forEach(hero => {
			console.log(hero);
		});
	
	```
	위처럼 `for` 문을 보다 간결하게 작성할 수 있음.


	## map
	```javascript
		const array = [1, 2, 3, 4, 5, 6, 7, 8];

		const squared = [];

		for (let i = 0; i < array.length; i++) {
			squared.push(array[i] * array[i]);
		}
		
		const square = n => n * n;
		const squared = array.map(square);


	```
	위 코드에서 볼 수 있듯이, 두줄로 더 간단한 코드를 작성할 수 있음