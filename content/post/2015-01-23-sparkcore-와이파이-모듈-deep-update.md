---
title: SparkCore 와이파이 모듈 deep update
author: openmicrolab
type: post
date: 2015-01-23T06:36:43+00:00
url: /sparkcore-와이파이-모듈-deep-update/
categories:
  - Wireless
  - Wi-Fi
  - Development
tags:
  - WIFI
  - SparkCore
  - 와이파이 모듈
  - deep update

---
CLI를 통해 <a href="https://www.spark.io/" target="_blank">SparkCore</a>의 내부 펌웨어 업데이트 순서

#### 1. Spark CLI 설치

[node.js][1] 설치

> $ sudo npm install -g spark-cli
> 
> $ spark cloud login

#### 2. <a href="http://openmicrolab.com/dfu-util-device-firmware-upgrade-utilities/" target="_blank">dfu-util  설치</a>

> brew install dfu-util

#### 3. 디바이스를 dfu mode로 진입

USB 케이블을 연결 후 Mode 버튼과 Reset 버튼을 동시에 누른후 Reset  버튼을 뗀다.

다음 커멘드를 실행한다.

> spark flash &#8211;usb deep\_update\_2014_06

참고: <a href="https://github.com/spark/spark-cli#performing-a-deep-update" target="_blank">https://github.com/spark/spark-cli#performing-a-deep-update</a>

 [1]: http://nodejs.org/