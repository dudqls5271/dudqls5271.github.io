---
title: Github Page와 Hexo 유용한 플러그인 설치
tags: [hexo]
---

### SED

SEO란?:
영어로 Search Engine Optimization로 대부분 검색엔진 최적화(SEO)와 관련되어있다.

### 플러그인 설치 or 삭제

> $ npm install -save

### 삭제

> $ npm uninstall

---

### hexo-autonofollow

이 플러그인은 rel="external nofollow" 속성을 추가하여 외부 링크 크롤링을 막아 준다고 한다.

```bash
   $ npm install hexo-autonofollow --save

```

```bash
nofollow:
enable: true
exclude:
- exclude1.com
- exclude2.com
```

### hexo-auto-canonical

이 플러그인은 대표 URL을 지정해준다고 한다.

```bash
    npm install --save hexo-auto-canonical
```

```bash
 <%- autoCanonical(config, page) %>
```

나는 head.ejs안에 위의 코드를 넣었다, 근데 테마마다 다름으로 주위 해줘야한다.
Control + P 을 누르면 파일 검색이 가능하다.

### hexo-generator-seo-friendly-sitemap

이 플러그인은 더욱 효율적으로 크롤링을 할 수 있도록 사이트맵 xml 파일을 자동으로 생성해 주는 것 이다.

```bash
    $ npm install hexo-generator-seo-friendly-sitemap --save
```

\_config.yml에 아래 코드를 추가 해준다.

```bash
# sitemap auto generator
sitemap:
    path: sitemap.xml
```

### hexo-generator-feed

RSS 피드를 만들어서 일종의 블로그 구독기능을 만들어 주는 것이다.

```bash
    npm install hexo-generator-feed --save
```

\_config.yml에 아래 내용을 추가 해준다.

```bash
    # rss feed auto generator
feed:
  type: rss2
  path: rss2.xml
  limit: 20
```

각각
type : feed의 종류 (atom/rss2) - \* 네이버는 atom을 지원하지 않음
path : feed가 생성될 경로(default : atom.xml, rss2.xml)
limit : 최신 포스트 수 설정 (0 또는 false - 전체 포스트)

### hexo-asset-link _필수 설치_

말 그래도 이 플러그인은 필수 설치이다.
내가 평소에 md파일에 글을 올리때 vs코드를 사용하는데, 이미지를 올릴때는 Github에 들어가서 이미지 파일을 따로 넣어줘야 했는데 이 플러그인을 설치해주면

md파일이 있는곳에 포스트의 이름과 동의한 폴더를 만들고 이미지를 넣어주면 아래와 같이 나온다.

```bash
+-- _posts/
|   +-- hexo_insatall.md
|   +-- hexo_insatall/
|       +-- Test-Image.png
|       +-- Test-Other-File.pdf
```

그러면 이제 이미지에 접근할때

!"[이미지 설명]"(Test-Image)
으로 간단하게 접근이 가능해진다.

자세한 설명은 [여기](https://www.npmjs.com/package/hexo-asset-link)에서 확인할 수 있다.

---
