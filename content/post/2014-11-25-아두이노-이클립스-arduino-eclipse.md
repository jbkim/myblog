---
title: '아두이노 & 이클립스 (Arduino & Eclipse)'
author: openmicrolab
type: post
date: 2014-11-25T06:07:29+00:00
url: /아두이노-이클립스-arduino-eclipse/
categories:
  - Open Source Hardware
  - Development
  - Tool
tags:
  - Arduino
  - 아두이노
  - 이클립스
  - Eclipse

---
지난번 포스팅 <a href="http://openmicrolab.com/%EC%9D%B4%ED%81%B4%EB%A6%BD%EC%8A%A4eclipse%EC%97%90%EC%84%9C-%EC%95%84%EB%91%90%EC%9D%B4%EB%85%B8arduino%EC%82%AC%EC%9A%A9%ED%95%98%EA%B8%B0/" target="_blank">&#8216;이클립스(Eclipse)에서 아두이노(Arduino)사용하기&#8217;</a> 은 이클립스에서 플러그인을 설치해서 아두이노를 사용하는 것이었다. 하지만 아두이노는 command line에서 컴파일을 지원하므로 이런 플러그인 없이도 make 파일의 위치, 컴파일러 정보등만 이클립스에 설정하면 사용이 가능하다.

### 1. 프로젝트 만들기

File > New > Makefile Project with Existing Code를 선택후 Project Name을 설정하고 Existing Code Location을 설정한다.

### 2. Project Properties

C/C++ Build항목에서 Build location의 Build directoty 설정은 makefile이 있는 위치를 지정한다.

C/C++ General 항목의 Path and Symbols에서 Include할 폴더들을 입력하고  Symbol에도 미리 정의돼야 할 심볼을 입력한다.

### 3. MakeFile

정작중요한 것은 MakeFile이다. 여기에 제대로된 설정이 되어 있는지 확인해야 함.<img loading="lazy" class="alignnone" src="http://openmicrolab.cdn2.cafe24.com/eclipse_arduino.png" alt="" width="1454" height="1047" />