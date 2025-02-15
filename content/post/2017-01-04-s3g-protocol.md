---
title: S3G protocol
author: openmicrolab
type: post
date: 2017-01-04T06:20:13+00:00
url: /s3g-protocol/
categories:
  - 3D Printer
tags:
  - 3d printer
  - Makerbot
  - S3G protocol
  - X3G

---
  * S3G는 “Sanguino3 Gcode”의 줄임말로 3D 프린터를 제어하는 언어임.
  * 파일의 경우 .s3g를 사용하는데 MakerBot에서 이것을 차용하여 .x3g로 사용함.
  * 초기에 8비트 AVR의 성능때문에 사용함.
  * MakerBot의 경우 s3g, x3g파일을 처리할 수 있고, gcode를 이것으로 변환하는 translator를 내장하고 있음.
  * OctoPrint의 경우 <a href="http://plugins.octoprint.org/plugins/gpx/" target="_blank">GPX라는 플러그</a>인이 있고,  <a href="https://markwal.github.io/GpxUi/" target="_blank">GpxUI</a>라는 GUI wrapper도 있다.
  * 관련 소스는 <a href="https://github.com/markwal/GPX" target="_blank">https://github.com/markwal/GPX</a>

**S3G protocol**

  * 관련 문서 <a href="https://github.com/makerbot/s3g/blob/master/doc/s3gProtocol.md" target="_blank">https://github.com/makerbot/s3g/blob/master/doc/s3gProtocol.md</a>
  * S3G 파이선 라이브러리 <a href="https://github.com/makerbot/s3g" target="_blank">https://github.com/makerbot/s3g</a>

**구성 및 통신**

![][1] 

2가지 네트워크로 구성이 된다.

  * Host network: PC와 보드로 기본적으로 시리얼이다. 115200 or 38400 bps
  * Tool network: 보드와 툴사이로 RS485 사용

에러 방지를 위해 매 패킷의 마지막에 CRC를 사용

![][2]

 [1]: https://raw.githubusercontent.com/makerbot/s3g/master/doc/SystemArchitecture.png
 [2]: https://raw.githubusercontent.com/makerbot/s3g/master/doc/HostToolCommandSuccess.png