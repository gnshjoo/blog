---
title: "Github 저장소"
date: 2023-01-06T17:49:06+09:00
draft: true
images:
  - /images/blog/logo.png
---

Github에서 특정 프로젝트를 포크하면, 원본 저장소를 자신의 저장소로 복사합니다. 이제 옮겨진 저장소에 기능을 추가하거나 내용을 수정하고 커밋하더라도 원본 저장소와는 분리 되어 있으므로 영향을 끼치지 않습니다.

 

포크한 저장소를 원본 저장소와 동기화 하는 방법을 알아보고자 합니다.

 

Github 원본 저장소의 주소 추가

```shell
git remote -v
```
 

원본 저장소 위치를 추가합니다.

```
git remove add upstream [원본 저장소]
```
 

원본 저장소 내용을 fecth 하고, master 브랜치로 체크아웃 합니다.

```
git fetch upstream
git checkout master
```

로컬 master 브랜치와 원본 저장소 master 브랜치 병합합니다

```
git merge upstream/master
```

로컬 master 브랜치를 push하면 자신의 github 저장소 내용이 원본 저장소와 최시 동기화 된 상태가 됩니다.

```
git push origin
```