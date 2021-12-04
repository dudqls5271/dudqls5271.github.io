---
title: 서버셋팅 - mysql7설치
tags: [서버, server, CentOS7, Linux, mysql]
---

저번 포스팅에서올렸던 CentOs7을 설치를 완료 했다면 이제는 mysql을 설치 할 순서 이다.

여기서 mnysql 이란?
mysql은 전세계적으로 가장 널리 사용되고 있고 있는 오픈 소스 데이터베이스이며, MySqLAB사가 개발하여 배포/판매하고 있는 데이터베이스(DateBase)이다.
표준 데이터베이스 질의 언어 SQL(Structured Query Language)을 사용하는 개방 소스의 관계형 데이터베이스 관리
관리시스템(RDBMS), 메우 빠르고, 유연하며, 사용하기 쉽다는 장접을 가지고 있다.

PHP 웹 프로그래밍에서 사용되는 DBMS는 MySQL이며, MySQL이 가지고 있는 특징을 살펴보면, 가장 먼저 꼽을 수 있는 것은 일반 사용자가 무료로 다운로드하여 사용할 수 있는 장점이다
MySQL은 공개용 소프트웨어이기 때문에 누구나 무료로 다운로드받아 사용 할 수 있지만, 상업적인 목적으로 MySQL을 사용하려면 반드시 라이센스를 별도로 구매하여야 한다. MySQL은 무료이면서 처리되는 속도 또한 상당히 빠르고 용이하며, 대용량의 데이터를 처리할 수 있는 장점과 보안에도 뛰어난 특성을 지니고 있습니다.

>데이터베이스 란?
>어느 한 조직의 여러 응용 시스템이 공유할 수 있도록 통합. 저장된 운영 데이터의 집합을 의미한다.

이제 아래의 방법대로 mysql을 설치를 해보자 오늘은 설치할 것이 많다 잘 따라와야 한다.

mysql을 설치 하기 전에 <b>yum update</b>로 업데이트가 있는지 확인 한다.
![image](https://user-images.githubusercontent.com/49426352/144710965-30af2566-0f86-494c-ac2d-8d04d528bd02.png)

다음은 wget을 설치 해준다.
<span style="color:red;"><b>yum install wget</b></span>
![image](https://user-images.githubusercontent.com/49426352/144710967-46322e7c-6eac-447b-8059-5a3f3baa5a77.png)

gcc -gcc-c++을 설치해준다.(컴파일러) 
<span style="color:red;"><b>yum install gcc gcc-c++</b></span>
![image](https://user-images.githubusercontent.com/49426352/144710970-fcd53590-5893-4626-8004-8faef9231ccf.png)

ifconfig는 네트워크 인터페이스 구성을 위한 유닉스 계열 운영체제의 시스템 관리 유틸리티이다
net-tools을 설치 해준다.(ifconfig)
<span style="color:red;"><b>yum install net-tools</b></span>
![image](https://user-images.githubusercontent.com/49426352/144710971-6078034f-43f9-4679-97be-ccb4a084e640.png)

mysql을 다운로드 해준다.
<span style="color:red;"><b>wget https://dev.mysql.com/get/mysql57-community-release-el7-11.noarch.rpm</b></span>
![image](https://user-images.githubusercontent.com/49426352/144710973-af4b3c23-03a0-4306-b91d-fb1d731b7acb.png)

mysql 설치
<span style="color:red;"><b>rpm -ivh mysql57-community-release-el7-11.noarch.rpm</b></span>
![image](https://user-images.githubusercontent.com/49426352/144710974-0d5b5618-db3a-4a9d-b84c-4634a259f05e.png)

mysql-server 설치
<span style="color:red;"><b>yum install mysql-server</b></span> 아래 사진 처럼 중간에 나오는 것은 y로
![image](https://user-images.githubusercontent.com/49426352/144710976-2923dc1e-e877-4524-9a38-0e54a35dc0a0.png)
![image](https://user-images.githubusercontent.com/49426352/144710979-bf6c7a27-afb3-4e60-9d71-f044f9c5d007.png)

mysql 서버 시작
![image](https://user-images.githubusercontent.com/49426352/144710983-8943fc97-0463-45aa-bb11-925103ae5711.png)

mysql 초기암호 확인법
<span style="color:red;"><b>cat /var/log/mysqld.log | grep 'temporary password'</b></span> 
![image](https://user-images.githubusercontent.com/49426352/144710987-3b71a176-bb9f-4593-b455-befcdbf071fc.png)

mysql 비밀번호 변경
<span style="color:red;"><b>mysql_secure_installation</b></span> 
![image](https://user-images.githubusercontent.com/49426352/144710988-c5388061-1e94-4e04-97de-2b5a23e8fe37.png)

비밀번호를 변경 후 각종 권한 설정이 나오는데
전부 Y눌러주면 된다.
![image](https://user-images.githubusercontent.com/49426352/144710990-4af19b7e-00e5-497f-a4c7-50cd810181c7.png)

mysql 설치 완료 후 접속
<span style="color:red;"><b>mysql -u root -p</b></span>을 입력하면 비밀번호를 입력하라고 나오는데 이때 비밀번호는 아까 설정해준 비밀번호를 입력해주면 된다.
![image](https://user-images.githubusercontent.com/49426352/144710991-ba5b2033-d412-41d9-96e9-ec67a50f7325.png)

mysql user 계정 추가 하기
<b><span style="color:red;">CREATE USER '</span><span style="color:blue;">[사용자 이름]</span><span style="color:red;">'@'</span><span style="color:red;">[주소]identified by '</span><span style="color:blue;">[비밀번호]<span style="color:red;">';</span></b>
![image](https://user-images.githubusercontent.com/49426352/144710994-67e2b83d-200e-4906-9335-99beaf42e72b.png)

스키마 생성
<b><span style="color:red;">create database</span> <span style="color:blue;">[스키마 이름]</span></b>
![image](https://user-images.githubusercontent.com/49426352/144710995-5bc78848-9d33-4286-b558-7579a1ea13f6.png)

mysql user 권한 추가
<b><span style="color:red;">grant all privileges on</span> <span style="color:blue;">[스키마]</span><span style="color:red;">.* to '</span><span style="color:blue;">[사용자 이름]</span><span style="color:red;">'@'</span><span style="color:blue;">192.168.0.%</span><span style="color:red;">'</span></b>
<b>여기서 '192.168.0.%'이 부분을 설명하자면 mysql에서 192.168.0.~로 시작하는 모든 IP에 원격 접속을 허용한다는 말</b>
![image](https://user-images.githubusercontent.com/49426352/144710996-038c4398-5762-436d-92eb-c21194c12155.png)

방화벽 포트 추가하기 mysql port 번호는 3306임으로 3306port를 열어주었다.
포트 추가
<b><span style="color:red;">firewall-cmd --zone=public --add-port=3600/tcp --permanent</span></b>
방화벽 재시작 (방화벽 설정 후 재시작을 해야 적용이 된다.)
<b><span style="color:red;">firewall-cmd --reload</span></b>
![image](https://user-images.githubusercontent.com/49426352/144711001-b694a62c-0a4a-4250-bcc9-51c3321a3ea0.png)

이상 mysql 설치를 마친다.