---
title: BBC Microbit 오프라인에서 사용하기
author: openmicrolab
type: post
date: 2016-09-16T09:43:18+00:00
url: /bbc-microbit-오프라인에서-사용하기/
categories:
  - ARM
  - mbed
  - Microbit
  - Development
  - Tool
tags:
  - mbed
  - microbit
  - 오프라인
  - offline

---
BBC microbit를 오프라인에서 사용하려면 <a href="http://yottadocs.mbed.com/#installing" target="_blank">링크</a>를 참고 하고 Manuall Installation 항목을 따라서 환경을 셋업한다.

**1. yotta설치**

Mac OS의 경우

> brew tap ARMmbed/homebrew-formulae  
> brew install python cmake ninja arm-none-eabi-gcc  
> pip install yotta

**Trouble shooting**  
brew 관련 아래과 같은 문제가 있을 경우  


> sudo chown -R $(whoami):admin /usr/local  
> cd $(brew &#8211;prefix) && git fetch origin && git reset &#8211;hard origin/master

**터미널에서 다음과 같은 에러메시지가 나올때**  
error: connection error: (&#8220;bad handshake: Error([(&#8216;SSL routines&#8217;, &#8216;ssl3\_get\_server_certificate&#8217;, &#8216;certificate verify failed&#8217;)],)&#8221;,)

> pip install -U certifi

참고: <a href="https://github.com/ARMmbed/yotta/issues/744" target="_blank">https://github.com/ARMmbed/yotta/issues/744</a>

**2. Srecord 설치**

> brew install srecord

**3. 예제 코드 받기**

> git clone https://github.com/lancaster-university/microbit-samples  
> cd microbit-samples

**4. 타겟을 miccrobit로 설정**

> yt target bbc-microbit-classic-gcc

**5. 프로젝트 빌드**

> yt build

**6. 마이크로비트에 다운로드 하기**  
마이크로비트는 MICROBIT라는 이름의 외장디바이스로 되어 있으니 hex파일을 copy하면 된다.

> cp ./build/bbc-microbit-classic-gcc/source/microbit-samples-combined.hex /Volumes/&#8221;MICROBIT&#8221;

**참고**  
<a href="https://lancaster-university.github.io/microbit-docs/offline-toolchains/" target="_blank">https://lancaster-university.github.io/microbit-docs/offline-toolchains/</a>  
<a href="http://yottadocs.mbed.com/#installing" target="_blank">http://yottadocs.mbed.com/#installing</a>