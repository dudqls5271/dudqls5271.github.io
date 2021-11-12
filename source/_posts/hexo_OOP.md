---
title: 겍채지향 프로그래밍 이란?
tags: [java, OOP]
---

# 객채 지향 프로그래밍

객체 지향 프로그래밍(이하 OOP)는 컴퓨터 프로그램을 “객체(Object)"들의 모임으로
파악하고자 하는 프로그래밍의 패러다임 중에 하나이다. 각 “객체(Object)" 들은 서로 메시지를
주고 받을 수 있으며 데이터를 처리할 수 있다.

### 객체 지향 프로그래밍(OOP)의 장점은

- 프로그램을 유연하고 변경이 용이하게 만든다.
- 프로그램의 개발과 보수를 간편하게 만든다
- 직관적인 코드 분석을 가능하게 한다.

<!--more-->

객체 지향 프로그래밍의 중요한 특성은 **\_강한 응집력(Strong Cohesion)과 약한 결합력(Weak Coupling)을 지향한다는** 점이다.

**응집력(Strong Cohesion)**

> 프로그램의 한 요소가 특정 목적을 위해 밀접하게 연관된 기능들이 모여서 구현되어 있고, 지나치게 많은 일을 하지 않으면 그것을 응집력이 높다고 표현한다.

**결합력(coupling)**

> 프로그램 코드의 한 요소가 다른 것과 얼마나 강력하게 연결되어 있는지, 얼마나 의존적인지를 나타내는 정도. 결합력이 낮다는 것은 한 요소가 다른 요소들과 관계를 크게 맺고 있지 않은 상태를 의미한다.

![download](https://user-images.githubusercontent.com/49426352/118004452-7088ca80-b384-11eb-85bd-46e73b50ef72.jpg)

필드에 몬스터들을 배치하고 싶다.
몬스터의 종류는 파랑 버섯, 주황 버섯, 뿔 버섯, 좀비 버섯이 있다.
각 몬스터들은 시간이 흐르고 래벨업을 할 수 있다.

### OOP의 기본 구성 요소

- 클래스(Class)
  같은 종류의 집단에 속하는 속성과 행위를 정의한 것.
  다른 클래스와 독립적으로 만들어줘야 한다.
  위의 예제에서 몬스터의 특성과 행위들을 정의한 객체가 클래스가 될 것이다.

- 객체(Object)
  클래스의 인스턴스(Instance). 상위 클래스의 속성을 가지고 있으면서 개별적인 특성과
  행위 (메서드 : Method)또한 가지고 있다.

- 메서드(Method)
  클래스로부터 생성된 객체를 사용하는 방법. 객체의 속성을 조작하는 데 사용한다.
  위의 예제에서 각각의 몬스터들이 레벨업을 하는 행위가 메서드(Method)라고 볼 수 있다.

# OOP의 특성

### 캡슐화(Encapsulation)

캡슐화는 객체의 데이터를 외부에서 직접 접근하지 못하게 막고, 함수를 통해서만 조작이 가능한 작업이다.

몬스터 레벨(Lv)과 같은 경우는 이용자가 입의로 조작하게 만들면 문제가 생길 가능성이 있기에, 그래서 래벨업(LvUp)이라는 함수를 통해서만 레벨업이 가능하도록 해야한다.

### 추상화(Abstraction)

추상화는 객체들이 가진 공통의 특성들을 파악하고 불필요한 특성들을 제거 하는 과정을 말한다.

객체들이 가진 동작들을 기준으로 이용자들이 동작만 쉽게 구동할 수 있도록 한다
레벨업(LvUp) 메소드를 실행만 하면 Lv이라는 속성을 컨트롤 할 수 있었던 것처럼.

이러한 추상화 과정을 통해 이용자들은 프로그래머가 만든 객체를 더 쉽게 사용할 수 있게 된다.

추상화를 할 때 주의할 점은 <b style="color: red">속성 위주가 아닌 동작 위주로 정의 하는 작업을 하는 것</b>이다.

어떠한 동작과 속성을 정의하고 불필요한 정의들을 삭제하여 이용자가 편리하게 객체를 이용할 수 있도록 구성한 것이 추상화이다.

# 객체지향 프로그래밍 VS 클래스 기반 프로그래밍

클래스 단위 프로그래밍과 객체지향 프로그래밍이 똑같은 내용인지 알고 있는 사람들이 있는데 일부는 맞고 일부는 틀리다.

### <span style="color:#5058bd;">엄격한 의미에서 해석</span>

객체지향 프로그래밍은 네가지특징(_추상화, 캡슐화, 상속, 다향성_)을 골고루 사용해 프로그램을 만드는것을 객체지향이라고 한다. 하지만 클래스 단위 프로그래밍은 이런 객체지향의 특징을 전혀 사용하지 않고 오직 클래스만을 이용해 프로그래밍 하는 방식을 말한다.

### <span style="color:#5058bd;">유연한 의미에서 해석</span>

클래스 단위 프로그램을 객체지향 프로그램이라고 부를 수 있는 이유는 클래스를 만들어 프로그래밍 하는 자체에 이미 객체지향 프로그래밍에 포함 되는 구조를 가지고 있다고 한다.

| 구분                       | 절차 지향 프로그래밍                                                             | 객체 지향 프로그래밍                                                                              |
| -------------------------- | -------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| <center>처리 방식</center> | <center>문제를 여러 개의 함수로 나누어순차적으로 호출하여 처리하는 방식</center> | <center>문제를 여러개의 <span style="color:red">객체</span> 단위로 나누어 처리 하는 방식</center> |
| <center>단점</center>      | <center>오래된 방식이며 협업해서 진행하는 큰 프로젝트에는 적합하지 않음</center> | <center>학습 난이도가 눞음. <br>개발자의 활용능력이 중요함</center>                               |
| <center>장점</center>      | <center>간단하고 소규모 프로젝트에 용이함.<br> 비교적 배우기 쉬움</center>       | <center>최근 가장 많이 사용하는 방식임. <br> 협업이 중요한 대형 프로젝트에 적합함<center>         |