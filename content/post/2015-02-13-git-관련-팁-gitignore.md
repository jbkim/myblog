---
title: git 관련 팁 – .gitignore
author: openmicrolab
type: post
date: 2015-02-13T01:06:53+00:00
url: /git-관련-팁-gitignore/
categories:
  - Infomation
  - Development
  - Tip
  - Uncategorized
tags:
  - Git
  - github
  - .gitignore

---
.gitignore를 설정 전에 원하지 않는 파일(예를 들면 소스가 아닌 컴파일된 obj 파일 같은..)이 repositary에 add/initilized된 경우는 cache를 지우고 tracking을 다시 설정해야 한다.  
먼저 필요한 파일들을 commit한후 다음의 명령어를 실행한다.  
cache 삭제

> git rm -r &#8211;cached .

다시 tracking 하도록 설정

> git add .

그 다음 commit

> git commit -m &#8220;.gitignore is now working&#8221;