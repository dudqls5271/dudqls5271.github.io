---
title: 자바 - 3. 기본형(primitive type)
tags: [java]
---

## 논리형(boolean)

논리형(boolean)에서는 한가지 밖에 없다 boolean형 변수에서는 true와 false중 하나를 저장할 수 있으며 기본값은 default 이다.

boolean형 변수는 대답(yes/no), 스위치(on/off) 등 논리구현에 주로 사용한다. 그리고 boolean형은 true와 false 두가지 값만을 표기 할수 있음으로 1bit만으로도 추운하지만, 자바에서는 데이터를 다루는 최소 단위가 byte이기 때문에, boolean의 크기가 1 byte이다.

아래 문장은 power라는 boolean형 변수를 선언하고 true로 변수를 초기화 한것이다.

```java
    boolean power = true;
    boolean power = False;      //오류 true와 false는 대소문자가 구분이 된다.
```

## 문자형(char)

문자형도 boolean과 같이 한가지 자료형 밖에 없다. 문자를 작성하기 위한 변수이기 때문에 char형은 문자형만 저장 할 수 있다. 아래 문장은 char타입의 변수 ch을 선언 한 것이다.

```java
    char ch = "A";
    char ch = "123";    // ""을 이용해 문자형으로 만들어 줌
    char ch = 123;      //오류 숫자형은 문자형인 char에 저장 되지 않는다.
```

## 정수형(byte, short, int long)

정수형에는 byte, short, int long가 있고
