---
title: CH340 USB to Serial driver
author: openmicrolab
type: post
date: 2017-06-16T01:39:01+00:00
url: /ch340-usb-serial-driver/
categories:
  - Development
tags:
  - ch340
  - ch341
  - usb to serial

---
WCH라는 중국회사의 CH340시리즈의 맥용 USB to Serial Driver.

<a href="http://www.wch.cn/download/CH341SER_MAC_ZIP.html" target="_blank" rel="noopener noreferrer">http://www.wch.cn/download/CH341SER_MAC_ZIP.html</a>

만약 설치에 문제가 발생하면, 다음과 같은 작업을 한후 다시 설치한다.

1. 기존 드라이버 제거

`sudo rm -rf /System/Library/Extensions/usb.kext`

`sudo rm -rf /Library/Extensions/usbserial.kext`

2. 맥을 재시작

3. 드라이버 패키지 파일 재설치

4. 재부팅