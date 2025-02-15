---
title: Mac OS X 커맨드라인에서 Gatekeeper 기능 설정
author: openmicrolab
type: post
date: 2016-12-06T01:46:44+00:00
url: /mac-os-x-커맨드라인에서-gatekeeper-기능-설정/
categories:
  - Infomation
  - Development
tags:
  - Mac OS X
  - Gatekeeper

---
애플 앱 스토어가 아닌 다른 경로로 프로그램을 다운로드해서 인스톨시 문제가 생기는 경우, 대부분의 경우 원인은 Gatekeeper가 enable되어서 생기는 문제.

현재 상태확인

> spctl &#8211;status

비활성화 & 활성화

> sudo spctl &#8211;master-disable
> 
> sudo spctl &#8211;master-enable

&nbsp;