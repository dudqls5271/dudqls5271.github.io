---
title: 자바 - 5.논리 연산자.
tags: [java]
---

## 논리 연산자 - &&, ||, !

논리 연산자는 '&&'는 우리말로 그리고(AND)에 해당하며, 두 피연샂자가 모두 true일 떄 만 true를 결과로 얻는다. '||'는 또는(OR)에 해당하며, 두 피연산자 중 어느 한쪽 만 true이여도 true를 결과로 얻는다. 그리고 논리 연산자는 피연산자로 boolean형 또는 boolean형 값을 결과로 하는 조건식만 허용한다.

> || (OR결합) 피연산자 중 어느 한쪽 truen이면 true를 결과로 얻는다.
> && (AND결합) 피연산자 중 양쪽 모두 true이어야 true를 결과로 얻는다.

논리 연산자의 피연산자가 '참(true)'인 경우와 '거짓(false)'인 경우의 연산결과를 표로 나타내면 다음과 같다고 할 수 있다.

| X     | Y     | X OR Y | X AND Y |
| ----- | ----- | ------ | ------- |
| true  | true  | true   | true    |
| true  | false | true   | false   |
| false | true  | true   | false   |
| false | false | false  | false   |

위 표에서 보는 것이 잘 보기 힘들다면 다음 과 같이 생각하면 편 할 것이다.

| X           | Y     | X OR Y      |
| ----------- | ----- | ----------- |
| <b>true</b> | true  | <b>true</b> |
| <b>true</b> | false | <b>true</b> |

| X            | Y     | X AND Y      |
| ------------ | ----- | ------------ |
| <b>false</b> | true  | <b>false</b> |
| <b>false</b> | false | <b>false</b> |

> OR(||)일 때는 x가 true 면 무조건 true
> AND(&&일 떄는 x가 false면 무조건 false

## 논리 부정 연산자 !

이 연산자는 피연산자가 true면 false를, false면 true를 결과로 반환한다. 간단히 말해서 true와 false를 반대로 바꾸는 것이다.

| X     | !x    |
| ----- | ----- |
| false | true  |
| true  | false |

## 비트 연산자 & | ^ ~ << >>

비트 연산자는 피연산자를 비트단위로 논리 연산한다. 피연산자를 이진수로 표현했을 때 의 가 자리가 아래의 규칙에 따라 연산을 수행한다. 피연산자로 실수는 허용하지 않는다
| X | !x |
| ----- | ----- |
| false | true |
| true | false |
