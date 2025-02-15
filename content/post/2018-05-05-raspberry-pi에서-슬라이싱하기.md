---
title: Raspberry Pi에서 슬라이싱하기
author: openmicrolab
type: post
date: 2018-05-05T03:51:23+00:00
url: /raspberry-pi에서-슬라이싱하기/
categories:
  - 3D Printer
tags:
  - Raspberry Pi
  - Octoprint
  - 3Dprint

---
<img loading="lazy" class="alignnone wp-image-4295" src="https://res.cloudinary.com/openmicrolab/image/upload/v1525492218/RPI_Sclicing_mqdbyg.png" width="662" height="342" />

Octoprint는 크로스플랫폼을 지원하며, Raspberry Pi를 기본적으로 지원한다.  이 <a href="https://hackaday.com/2018/05/03/3d-printering-which-raspberry-pi-is-best-at-slicing-in-octoprint/" target="_blank" rel="noopener noreferrer">기사</a>에서는 3가지 종류의 Raspberry Pi에서 슬라이싱 테스트를 했는데, 결론은 다음과 같다.

> There’s simply no competition between a modern desktop or laptop processor and the comparatively dinky ARM chip used in the Raspberry Pi. Which is why you should _really_ just slice your models on the computer and send the resulting G-Code to OctoPrint over the network. That’s the intended workflow, and it really does make a lot more sense than forcing the Pi to labor over a task it’s clearly not cut out for. If the results of this test have shown anything, it’s that slicing on the Pi is a time consuming process no matter which model you buy.

**즉 슬라이싱은 PC에서하고, Octoprint는 Gcode를 네트워크로 전달하는 역할만 하도록&#8230;**