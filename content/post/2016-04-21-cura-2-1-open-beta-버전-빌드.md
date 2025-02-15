---
title: Cura 2.1 open beta 버전 빌드
author: openmicrolab
type: post
date: 2016-04-21T06:03:26+00:00
url: /cura-2-1-open-beta-버전-빌드/
categories:
  - 3D Printer
  - Open Source Hardware
tags:
  - Mac OS X
  - 3d printer
  - Cura
  - 큐라
  - Cura 2.1 open beta
  - Cura 빌드

---
Ultimaker에서 기존 Cura와 다른 GUI를 가진 Cura를 개발해서 <a href="https://ultimaker.com/en/community/20538-cura-21-open-beta-has-been-released" target="_blank">베타버전</a>을 내놓았다. 이유는

> This is the new, shiny frontend for Cura. daid/Cura is the old legacy Cura that everyone knows and loves/hates.  
> We re-worked the whole GUI code at Ultimaker, because the old code started to become a unmaintainable

사실 daid의 Cura의 경우 맥에서의 빌드는 본인도 hell이라고 표현을 하는데, 이번 베타버전의 큐라를 빌드해 보니 스무스하게 빌드가 된다. 단 빌드 시간은 엄청나게 오래 걸린다.

<img loading="lazy" class="alignnone wp-image-3646" src="http://res.cloudinary.com/openmicrolab/image/upload/v1461218197/Cura_Beta_d5kxbm.png" alt="" width="1243" height="806" /> 

### Mac에서의 빌드 방법

#### 필요한 파일들 설치

  * xcode 설치
  * cmake 설치 &#8211; brew install cmake
  * openssl 설치 &#8211; brew install openssl
  * brew link openssl &#8211;force
  * gcc 설치 &#8211; brew install gcc

#### 빌드

  * git clone git@github.com:Ultimaker/cura-build.git
  * cd cura-build
  * mkdir build
  * cd build
  * cmake ..
  * make

#### 추가적인 머신 설정 방법

Json 파일을 만들어야 하는데, 맥에서의 파일 위치는 /Users/AteamRnd/Downloads/Cura.app/Contents/Resources/cura/resources/machines

<a href="https://ultimaker.com/en/resources/20406-installation-cura-2-1" target="_blank">베타버전의 메뉴얼</a>

다른 OS에서의 빌드는 <a href="https://github.com/Ultimaker/cura-build" target="_blank">링크</a>를 참고.

관련 내용: <a href="https://ultimaker.com/en/resources/20511-change-machine-settings" target="_blank">https://ultimaker.com/en/resources/20511-change-machine-settings</a>