---
title: Mac에서 .DS_Store 일괄 삭제 및 생성 방지하는 법
author: openmicrolab
type: post
date: 2014-05-07T02:17:10+00:00
url: /mac에서-ds_store-일괄-삭제-및-생성-방지하는-법/
dsq_thread_id:
  - "2676808945"
categories:
  - Infomation
  - Development
tags:
  - Mac
  - .DS_Store

---
### 일괄삭제

> sudo -s
> 
> find / -type f -name .DS_Store -print -delete

/ 부터 검색을 해서 .DS_Store가 발견이 되면 해당위치를 프린트하고 삭제를 한다.

### 생성 방지

> defaults write com.apple.desktopservices DSDontWriteNetworkStores true