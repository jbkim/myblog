---
title: Github – Fork한 저장소 업데이트하기
author: openmicrolab
type: post
date: 2014-11-14T12:33:03+00:00
url: /github-fork한-저장소-업데이트하기/
categories:
  - Development
  - Tip
tags:
  - github
  - Pork
  - fetch
  - checkout

---
Github에서 fork한 저장소를 원본 저장소와 연결해서 업데이트하려면, github에서 제공하는 툴에는 메뉴가 없으므로 터미널에서 작업을 해야한다.

### Remote 설정

현재 설정된 리모트 저장소를 확인

> $ git remote -v

새로운 리모트 업스트림을 추가

> $ git remote add upstream https://github.com/ORIGINAL\_OWNER/ORIGINAL\_REPOSITORY.git

추가된 리모트 저장소 확인

> $ git remote -v

다음과 같은 형태로 업스트림이 추가된 것을 볼 수 있다.

<img loading="lazy" class="alignnone" src="http://openmicrolab.cdn2.cafe24.com/git_remote_v.png" alt="" width="606" height="102" /> 

### Fork한 것을 업데이트

패치를 한다.

> $ git fetch upstream

그다음에 checkout&#8230; 일반적으로 master이고 내가 fork한 브랜치의 이름을 적어야 한다.

> $ git checkout master

merge를 한다. 이때도 일반적으로 master이고 내가 fork한 브랜치의 이름을 적어야 한다.

> $ git merge upstream/master

### Conflict 해결하기

충돌 상황을 확인

> $ git status

충돌이 생긴 파일의 시작 부분에 **<<<<<<< HEAD**, 끝 부분에 **>>>>>>>** 표시가 되어 있다. 이것을 해결한 후에 **git add** 명령으로 변경된 파일을 추가하고 **commit**를 하면 된다.