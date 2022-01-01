---
title: 서버셋팅 - 케리터셋 설정
tags: [서버, server, CentOS7, Linux, mysql]
---


한참 개발을 하다가 INSERT할 때 한글 깨짐 현상이 있어서 globals.properties에 URL 문제 인가 싶었지만 아니였다.
Mysql 접속 후 status을 입력하면 각각의 데이터 타입? 이 보일 것이다. 이 것들을 수정해 줘야 한다.

![image](https://user-images.githubusercontent.com/49426352/144711004-9d84c4eb-eb4f-4121-8720-0f13e6b9d092.png)
![image](https://user-images.githubusercontent.com/49426352/144711006-25031f20-ef3e-40b4-9ce0-acec76fee576.png)

exit로 mysql을 나가 준다음에
![image](https://user-images.githubusercontent.co m/49426352/144711009-b33528f4-b80d-45c3-b7a5-8675025e26c9.png)
