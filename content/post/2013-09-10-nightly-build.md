---
title: Nightly build
author: openmicrolab
type: post
date: 2013-09-10T02:04:33+00:00
url: /nightly-build/
dsq_thread_id:
  - "1745285183"
categories:
  - Infomation
  - Development
tags:
  - Nightly build

---
### Nightly build란?

오픈소스프로젝트의 소스를 다운로드하다보니 정식으로 릴리즈된 버젼이 있고, 그 밑에 Nightly build라는 것이 있다. 위키피디아에 찾아보니 다음과 같이 나온다.

> 소프트웨어 개발 단계에 따라 분류를 나눌 수 있다. 소프트웨어 배포자에 따라 이 소프트웨어 분류는 바뀔 수 있지만 일반적인 룰은 다음과 같다.
> 
>   1. 알파 버전: 개발 주기에서 알파 버전의 경우 내부 테스트용으로 공개하는 경우가 많다. 거의 모든 주요 기능을 포함하고 있지만 많은 버그가 존재하고 실제 사용자가 도입해서 사용하기에는 무리가 있는 버전을 말한다. 베타 버전 이전의 단계이다.
>   2. 베타 버전: 베타 버전의 경우 알파에서 나온 문제점들을 수정한 단계이고 외부로 공개 테스트를 시작할 수 있을 정도의 완성도를 가진 소프트웨어를 말한다. 이후로는 새로운 기능보다는 나온 문제점들을 수정하고 UI를 최적화 하는 작업을 진행한다.
>   3. RC (Release Candidate): RC는 Microsoft에서 사용하는 소프트웨어 개발 단계로 정식판이 배포되지 직전의 단계로 볼 수 있다. 일반적으로 베타와 정식 배포판의 중간단계에 해당한다.
>   4. Nightly build: 매일 발생하는 소프트웨어에 대한 수정사항을 포함하고 있는 소프트웨어 배포버전이다. 소프트웨어는 테스트가 되어 있지 않을 수 있기 때문에 매우 불안정한 상태이다.
> 
> 출처: <a href="http://ko.wikipedia.org/wiki/%EC%86%8C%ED%94%84%ED%8A%B8%EC%9B%A8%EC%96%B4" target="_blank">위키피디아(소프트웨어)</a>

영문 위키피디아에 보면 왜 nightly build라는 말을썼는지 이해가 더 쉬울듯&#8230;

> A **nightly build** is a neutral build that takes place automatically. These typically take place when no one is likely to be working in the office so that there are no changes to the [source code][1] during the build. The results of the build are inspected by the arriving programmers, who generally place a priority on ensuring the recent changes to the source code have not broken the build process or functionality of the software.

&nbsp;

 [1]: http://en.wikipedia.org/wiki/Source_code "Source code"