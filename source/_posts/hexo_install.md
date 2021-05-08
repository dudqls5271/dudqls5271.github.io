---
title: Github Page에 hexo 이용해서 만들기 블로그 만들기 (1)
tags: [hexo]
---

JAVA온라인스터디를 하면서 사람들이 Github로 블로그를 만드는 것을 보고 신기해서 만들게 되었다.
조금 검색 해보니깐 Github는 Github Pages애 블로그를 만들어 볼려고 한다. 조금 구글에서 검색해보니깐 대부분 hexo?을 많이 사용한다고 하길래 나도 한번 hexo을 이용해서 블로그를 만들어 볼려고 한다.

### 기본 설치 프로그램

vscode와 NodeJS을 깔아주었다.
[vscode](https://code.visualstudio.com/download), [NodeJS](https://nodejs.org/ko/) 다운 링크

![p2](https://user-images.githubusercontent.com/49426352/117543472-09070e00-b058-11eb-8d5e-d3ffd3693707.png)

NodeJs는 다음과 같이 cmd에 Node라고 처주면 설치확인이 가능하다.

### 1. 레포지터리 만들기

우선 github에 새로운 레포지터리를 만들어 준다.
![p1](https://user-images.githubusercontent.com/49426352/117542272-e9b9b200-b052-11eb-9ab4-2cbaae5240e8.png)

여기서 중요한것은 "자신의Github로ID".githud.io로 만들어줘야 한다는 점이다.
나의 Github로 보자면 dudqls5271.github.io가 되는것이다.

### 2. hexo 설치

다음 사진과 같이 입력 해주면 hexo 기본설치가 시작 된다.

```bash
$ hexo init
```

![화면 캡처 2021-05-08 233126](https://user-images.githubusercontent.com/49426352/117543483-14f2d000-b058-11eb-90ee-848b32980972.png)

설치가 완료 되면 다음과 같이 여러개의 폴더 들이 생긴 것을 볼 수가 있다.

마지막으로 아래을 입력해주면 hexo에 필요한 파일들이 설치가 된다.

```bash
$ npm install
```
![화면 캡처 2021-05-08 233215](https://user-images.githubusercontent.com/49426352/117543494-1cb27480-b058-11eb-87b3-c6412440b3b2.png)

### 3. 테마 설정

다음은 테마 설정이다.
테마는 다른 사람들이 만들어 준 테마를 사용하면된다. [[여기]](https://code.visualstudio.com/download)서 테마를 고를수 있다.
원하는 테마를 고른뒤 그 사람의 Github에 들어가서 URL을 복사 해준뒤

![화면 캡처 2021-05-08 234329](https://user-images.githubusercontent.com/49426352/117543513-2936cd00-b058-11eb-96ae-377f08cbf7d1.png)

```bash
$ cd themes
$ git clone 링크
```

그러면 themes에 추가가 된것을 볼 수 있을것이다.
에제 theme을 본인 마음대로 바꿔주면 된다.
