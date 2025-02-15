---
title: AVR Studio 4에서 Atmel Studio 7에서 마이그레이션
author: openmicrolab
type: post
date: 2018-03-28T02:16:21+00:00
url: /avr-studio-4에서-atmel-studio-7에서-마이그레이션/
categories:
  - Open Source Hardware
  - Development
tags:
  - AVR Studio 4
  - Atmel Studio 7
  - Jungo
  - AVRISP

---
AVR Studio 4에서는 AVRISP mkII의 윈도우즈 USB 디바이스 드라이버가 Jungo 드라이버로 장치관리자의 Jungo아래 WinDriver와 함께 설치가 된다. 하지만 Atmel Studio 7이 설치가 되면 이것이 삭제가 되면서 Atmel아래 AVRISP mkII가 생기면서 더이상 AVR Studio 4에서는 AVRISP mkII는 잡히지 않는다

<img loading="lazy" class="alignnone wp-image-4261" src="https://res.cloudinary.com/openmicrolab/image/upload/v1522203011/Jungo_eccmcw.png" width="229" height="214" /> 

문제는 Atmel Studio 7에서 오래전에 구매한 AVRISP mkII를 연결을 하니, firmware를 업데이트 하라고 나온다.

<img loading="lazy" class="alignnone wp-image-4262" src="https://res.cloudinary.com/openmicrolab/image/upload/v1522203018/avrisp_fwup_cvspmw.png" width="329" height="218" /> 

하지만 정품 툴이 아니라서 업데이트가 되지 않는다. 이것을 해결하려면 Tools > Options > Tool Settings >Check Firmware의 항목을 False로 하면 진행이 된다.

<img loading="lazy" class="alignnone wp-image-4263" src="https://res.cloudinary.com/openmicrolab/image/upload/v1522203019/avrISP_z8uwij.png" width="611" height="358" /> 

참고로 만약 지워진 AVR Studio 4의 Jungo 드라이버만 다시 설치를 하려면, C:\Program Files (x86)\Atmel\AVR Jungo USB\usb64 폴더에서 관리자 계정으로 커멘드 창에서 다음과 같은 명령으로 드라이버 설치가 가능하다.

> wdreg -inf windrvr6.inf install

**참고**: <a href="https://www.olimex.com/Products/AVR/Programmers/AVR-ISP-MK2/open-source-hardware" target="_blank" rel="noopener noreferrer">https://www.olimex.com/Products/AVR/Programmers/AVR-ISP-MK2/open-source-hardware</a>

<a href="http://openmicrolab.godohosting.com/Files/AvrStudio4Setup.zip" target="_blank" rel="noopener noreferrer">AVR Studio 4 다운로드</a>