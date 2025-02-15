---
title: AstroPrint 분석
author: openmicrolab
type: post
date: 2016-10-19T09:17:40+00:00
url: /astroprint-분석/
categories:
  - 3D Printer
tags:
  - 3D Printing
  - AstroPrint
  - Octoprint
  - Wireless 3D printing

---
원격 3D프린팅을 지원하는 기기인 <a href="https://www.astroprint.com/" target="_blank">AstroPrint</a> 분석

**1. 가격**

  * AstroPrint에서 파는 기기 &#8211; $149
  * Raspberry Pi 세트: $65
  * 지원하는 카메라: $30 ~ $68 (라즈베리용 카메라는 지원하지 않음)
  * 따라서 카메라 포함 가격은 $95 ~ $217 정도

**2. 카메라**

  * 카메라는 리눅스를 지원하는 USB카메라(Video for Linux v2)이어야 하며 웹에서 카메라 스트리밍을 보는 형태라서(WebRTC) FireFox, Chrome and Opera에서만 영상을 볼 수 있음
  * pcDuino 기반의 AstroPrint는 스트리밍 지원 안됨. <span style="text-decoration: underline;">즉 Raspberry Pi기반만 웹 스트리밍 지원</span>.
  * <a href="http://iswebrtcreadyyet.com/" target="_blank">WebRTC의 한계</a>: 브라우저 지원

**참고 자료: **<a href="https://blog.astroprint.com/live-video-streaming-is-now-available-on-astroprint/" target="_blank">https://blog.astroprint.com/live-video-streaming-is-now-available-on-astroprint/</a>