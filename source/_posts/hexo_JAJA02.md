---
title: 자바 - 2. 변수(Variable) 타입
tags: [java]
---

## 변수의 타입

우리가 주로 사용하는 값(data)의 종류(type)는 크게 '문자의 숫자'로 나눌 수 있으며, 숫자는 다시 '정수와 실수'로 나눌 수 있다.

<!--more-->

![그림2](https://user-images.githubusercontent.com/49426352/122957441-e8eb9e00-d3bc-11eb-9601-a1296d08178c.png)

이러한 값(data)의 종류(type)에 따라 값이 지정될 공간의 크기와 저장형식을 정의한 것 이 자료형(data type)이다. 자료형에는 문자형(char),정수형(dyte, short, int, long), 실수형 (float, double)등이 있으며, 변수를 선언할 때는 저장하는 값의 특성을 고려하여 가장 알맞은 자료형을 변수의 타입으로 선택하면 된다.

## 기본형과 참조형

자료형은 크게 '기본형'과 '참조형' 두 가지로 나눌 수 있는데, <b>기본형 변수는 실제 값(data)을 저장</b>하는 반면, <b>참조형 변수는</b>어떤 값이 저장되어 있는 <b>주소(memory address)를 값으로 갖는다.</b> 자바는 참조형 변수 간의 연산을 할 수 없으므로 실제 연산에 사용되는 것은 모두 기본형 변수 이다.

> 1. 기본형(primitive type)
>    논리형(boolean), 문자형(char), 정수형(byte, short, int, long), 실수형(float, double)
> 2. 참조형(reference type)
>    객체의 주소를 저장한다. 8개의 기본형을 제외한 나머지 타입.

참조형 변수(또는 참조변수)를 선언할 때는 변수의 타입으로 클래스의 이름을 사용하므로 클래스의 이름이 참조변수의 타입이 된다. 그래서 새로운 클래스를 작성한다는 것은 새로운 참조형을 추가하는 셈이다.

다음은 참조변수를 선언하는 방법이다. 기본형 변수와 같이 변수이름 앞에 타입을 적어 주는데 참조변수의 타입은 클래스의 이름이다.

> // 변수의 타입이 기본형이 아닌 것들은 모두 참조변수이다.
> 클래스이름 변수이름;

다음은 Data클래스 타입의 참조변수 today를 선언한 것이다. 참조변수는 null 또는 객체의 주소를 값으로 갖으며 참조변수의 초기화는 다음과 같다.

```java
    // Data객체를 생성해서, 그 주소를 today 저장
    Data today = new data();
```

객체를 생성하는 연산자 new의 경과는 생성된 객체의 주소이다. 이 주소가 대입연산자 "="에 의해서 참조변수 today에 저장되는 것이다. 이제 참조변수 today를 통해서 생성된 객체를 사용할 수 있게 된다.

## 상수(constant)

'상수(constant)'는 변수와 마찬가지로 '값을 지정할 수 있는 공간'이지만, 변수와 동일하며, 단지 변수의 타입 앞에 키워드 'final'을 붙여주기만 하면 된다.

```java
    // 상수 MAX_SPEED을 선언 & 초기화
    final int MAX_SPEED = 10;
```

<b>그리고 상수는 반드시 신언과 동시에 초기와해야 하며</b>, 그 이후 부터는 <b> 상수의 값을 변경하는 것이 허용되지 않는다.</b>

```java
    final int MAX_SPEED;        // 에러. 상수는 선언과 동시에 초기화 해야한다.
    final int MAX_VALUE = 100;  // OK. 선언와 동시에 초기화했음
    MAX_VALUE = 200;            // 에러. 상수 값은 변경할 수 없음
```

상수의 이름은 <b>모두 대문자로 하는 것이 암목적인 관례이며</b> (이건 나도 몰랐네여), <b>여러 단어로 이루어 져있는 경우 '\_'로 구분한다.</b>

## 리터럴(literal)

프로그래밍 상의 상수는 '값을 한 번 저장하면 변경할 수 없는 저장공간'으로 정의가 되어있기에 이와 구분하기 위해서 상수를 '리터럴'이라는 용어를 사용한다.

> 변수(variable) 하나의 값을 저장하기 위한 공간
> 상수(constant) 값을 한번만 저장할 수 있는 공간
> 리터럴(literal) 그 자체로 값을 의미 하는 것
