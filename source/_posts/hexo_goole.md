---
title: Hexo - 검색엔진 최적화
tags: [hexo]
---

## 검색 엔진 최적화(SEO)

블로그 생성 후 내가 작성한 포스트가 검색에 노출되기 위해서는 검색엔진에 노출 될 수 있도록 검색 엔진 최적화 작업을 진행해 주어야 한다.

> 검색 엔진 최적화(search engine optimization, SEO)는 웹 페이지 검색엔진이 자료를 수집하고 순위를 매기는 방식에 맞게 웹 페이지를 구성해서 검색 결과의 상위에 나올 수 있도록 하는 작업을 말한다. 웹 페이지와 관련된 검색어로 검색한 검색 결과 상위에 나오게 된다면 방문 트래픽이 늘어나기 때문에 효과적인 인터넷 마케팅 방법 중의 하나라고 할 수 있다. 기본적인 작업 방식은 특정한 검색어를 웹 페이지에 적절하게 배치하고 다른 웹 페이지에서 링크가 많이 연결되도록 하는 것이다. 구글 등장 이후 검색 엔진들이 콘텐츠의 신뢰도를 파악하는 기초적인 지표로 다른 웹사이트에 얼마나 인용되었나를 사용하기 때문에 타 사이트에 인용되는 횟수를 늘리는 방향으로 최적화 한다.
> </br> <b>위키백과검색</b> 엔진 최적화

## 검색엔진 최적화(SEO)에 유용한 플러그인 설치

HEXO에서는 SEO와 관련된 다양한 플로그인들이 있으며 그 중 몇 가지를 이용할 수 있도록 정리해 보았다.

- hexo-auto-canonical
- hexo-generator-robotstxt
- hexo-autonofollow
- hexo-generator-feed
- hexo-generator-seo-friendly-sitemap

```bash
$ npm install --save hexo-auto-canonical
```

- 사용
  -- 설치한 테마 내 HEAD태그 내 삽입해서 사용한다.
  -- 보통 <b style="color: red">themes > 본인 테마 이름 -> layout -> common -> head.ejs</b>
  -- 만약 위의 위치에 없으면 VS 코드 기준으로 <b style="color: red">Control + P</b>을 눌러서 head.ejs를 검색해보자

```htnl
head.ejs
  <%- autoCanonical(config, page) %>
```

## hexo-generator-robotstxt

자동으로 robot.txt 파일을 생성해주는 플러그인 이다.

> 로봇 배제 표준은 웹 사이트에 로봇이 접근하는 것을 방지하기 위한 규약으로, 일반적으로 접근 제한에 대한 설명을 robots.txt에 기술한다. 이 규약은 권고안이며, 로봇이 robots.txt 파일을 읽고 접근을 중지하는 것을 목적으로 한다. 따라서, 접근 방지 설정을 하였다고 해도, 다른 사람들이 그 파일에 접근할 수 있다. robots.txt 파일은 항상 사이트의 루트 디렉토리에 위치해야 한다.
> <b>위키백과로봇 배제</b> 표준

- 설치

```bash
$ npm install hexo-generator-robotstxt --save
```

- 사용
  이것도 자신의 theme의 \_config.yml에 넣어주면 된다.

```yml
nofollow:
  enable: true
  exclude:
    - exclude1.com
    - exclude2.com
```

## hexo-generator-feed

- 자동으로 RSS feed를 생성해주는 플러그인 이다.

> 어떤 사이트가 있을 때, 그 사이트를 매일 방문해서 재미있는 새로운 기사가 있는지 확인하는 것은 번거롭습니다. 특히 새 기사가 매일 또는 정기적으로 올라오는 것이 아니라 불규칙할 때는 더욱 그렇습니다.
> 그 사이트를 직접 방문하지 않고, 새 기사들만 자신의 컴퓨터로 “배달”이 된다면 편리할 것입니다.
> RSS(Really Simple Syndication 의 약자) 같은 “사이트 피드”란, 새 기사들의 제목만, 또는 새 기사들 전체를 뽑아서 하나의 파일로 만들어 놓은 것입니다.
> 이제 각 사이트들에서 제공하는 RSS파일 주소만 수집하여 확인하면, 자신의 취향에 맞는 새로운 읽을거리를 쉽게 찾아서 읽을 수 있습니다.
> 그러나 모든 사이트에서 RSS피드를 제공하는 것은 아닙니다. 1년 내내 새로운 내용이 없는 정적인 사이트에서는 제공하지 않는 것이 보통입니다. 새로운 읽을거리가 자주 올라오는 “뉴스형”, “블로그형” 사이트에서 주로 제공됩니다.</br> <b>RSS Feed</b>

- 설치

```bash
$ npm install hexo-generator-feed --save
```

- 사용

```yml
feed:
  type: rss2
  path: rss2.xml
  limit: 20
```

## 검색엔진 등록하기

- [구글 애널리틱스](https://analytics.google.com/)(Google Analytic)
  0
  - 위 사이트에서 가입을 하고 <b>이름과 URL</b>을 입력하고 <b>추척ID</b>를 발급 받는다. </br> 이 아이디는 themes의 <span style="color: red">\_config.yml</span> 내 <span style="color: red">google_analytics</span>에 넣어 준다.

가입이 완료 되면 다음과 같은 화면이 나오는것을 보게 될 것이다.
![화면 캡처 2021-06-03 230347](https://user-images.githubusercontent.com/49426352/120660092-f0a4da80-c4c1-11eb-8de1-2425caf96246.png)
![화면 캡처 2021-06-03 232412](https://user-images.githubusercontent.com/49426352/120661993-bb998780-c4c3-11eb-811c-0a5dadfc15e2.png)
![화면 캡처 2021-06-03 232435](https://user-images.githubusercontent.com/49426352/120661997-bccab480-c4c3-11eb-9012-8ead74c104d3.png)
![화면 캡처 2021-06-03 232755](https://user-images.githubusercontent.com/49426352/120662002-bd634b00-c4c3-11eb-9343-2e9c1a2a9171.png)

- 사용

```yml
plugins:
  google-analytics:
    # Google Analytics tracking id
    tracking_id: UA-*********-1
```
