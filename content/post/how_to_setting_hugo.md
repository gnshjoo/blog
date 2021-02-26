---
title: "Hugo 블로그 설정하기"
date: 2020-09-29T22:24:51+09:00
categories: ["blog"]
tags: ["hugo", "blog", "themes"]
cover: ""
draft: false
---

## 1. Hugo 시작하기

hugo는 Go로 제작되어서 배포됩니다.

## 2. OSX에 hugo 설치하기

```shell
    brew install hugo

    hugo new site blog
```

![Example image](/img/hugo_new_site.png)

초기화 된 프로젝트가 만들어집니다. config.toml 파일 하나가 만들어진다.

```shell
    hugo server -D
```

실행 후 **localhost:1313**으로 접속하면 아무 정보도 보이지 않는다. 아무런 정보가 보이지 않는 이유는 렌더링 할 내용이 없어서 이다.

## 3. 테마 적용하기

Hugo의 테마를 제공해주는 곳은 https://themes.gohugo.io 이곳에서 자신이 원하는 테마를 /themes 안으로 넣으면 된다.

그리고 그 넣은 테마의 config.toml에 따라서 설정해주면 된다. 설정은 각각의 themes에 docs에서 맞춰 설정하면 된다.

## 4. Local / github page에 배포하기

```shell
    hugo  # public 이라는 폴더에 사이트를 빌드한다.
    git submodule add <url> public # 자신의 git page repo를 submodule로 등록한다.
```

먼저 git page에 올리기 위해서는 정적 사이트로 빌드를 해줘야한다. 빌드 시 생기는 public 폴더 안에 정적 사이트가 생성되기 떄문에 git submodule를 통해 등록해 준다.

Hugo Docs에 https://gohugo.io/hosting-and-deployment/hosting-on-github/#put-it-into-a-script 배포할 수 있는 scprit로 배포를 편안하게 할 수 있으니 참고하도록 한다.
