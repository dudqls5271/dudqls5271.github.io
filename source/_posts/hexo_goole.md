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
