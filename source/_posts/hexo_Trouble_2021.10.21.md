---
title: 전화번호 11자리? 12자리?
tags: [트러블슈팅]
---

예전 전화번호는 01X - XXX - XXXX의 형식의 번호도 있었으나 
010이라는 번호가 적용되면서 01X 는 아직까지 있지만 01X - XXX - XXXX의 형태는 사라졌다고 한다. 
그러면 원래 01X - XXX - XXXX의 형태의 번호를 가지고 있던 사람의 번호는 어떻게 되는가? 
그것은 바로 원래 보유중이던 3자릿수에 맨 앞자리에 숫자를 추가하는 것이다.
ex) 01X - NXXX - XXXX 이런식으로 추가가 되는것이다.
<!--more-->
이 이야기를 왜 했느냐 그것은 10월21일에 사용자의 전화번호를 엑셀 데이터에 입력받아 DB에 업로드 하는 과정에서 일어난 일이다. DB상에서는 예를 들어서 컬럼이 companyPhone1, companyPhone2, companyPhone3 이런식으로 3개의 컬럼으로 각각 01X, XXXX, XXXX 로 구분을 해줬다. 
![KakaoTalk_20211103_195238880](https://user-images.githubusercontent.com/49426352/140048545-7f1663ba-5e63-434d-ac17-03498dc22496.png)

하지만 사용자 입장에서 엑셀에 적는 데이터는 대부분 01X - XXXX - XXXX이런 형식으로 하이폰(-)을 포함안  13수의 번호를 적게 된다.
![KakaoTalk_20211103_195437014](https://user-images.githubusercontent.com/49426352/140048553-709abab1-7812-4081-b19b-d7296e691b5a.png)


여기서는 대부분 subString로 잘라줘서 각각의 컬럼에 넣으면 된다고 하지만 중간 번호가 3자리면?

![KakaoTalk_20211103_195405923](https://user-images.githubusercontent.com/49426352/140048549-f1ef18b5-e47c-4f64-b22e-c83cc2ce2bac.png)

그러면 4자리 이니깐 XXX- 이런식으로 들어가고 마지막은 XXX 이런식으로 오류가 생기는게 뻔하다. 


처음에는 그것을 막는다고 번호를 배열로 바꾸고 그 길이를 저장하고 날리를 쳤지만 검색해보니 위와 같은 결과가 나와서 이제는 그냥 subString로 처리 하기로 했다.

