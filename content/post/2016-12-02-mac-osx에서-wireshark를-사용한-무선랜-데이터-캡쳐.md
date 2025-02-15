---
title: MAC OSX에서 Wireshark를 사용한 무선랜 데이터 캡쳐
author: openmicrolab
type: post
date: 2016-12-02T09:05:52+00:00
url: /mac-osx에서-wireshark를-사용한-무선랜-데이터-캡쳐/
categories:
  - Uncategorized
tags:
  - wireshark
  - 와이어샤크
  - wi-fi
  - 무선랜

---
<a href="https://wiki.wireshark.org/CaptureSetup/WLAN#Mac_OS_X" target="_blank">Wireshark wiki</a>에 monitor mode에 대한 설명이 나온다. 그런데 airport를 사용하는 내용이라서 별 의미가 없다. Wireshark에서 무선랜 데이터를 캡쳐하려면 monitor mode를 enable해야 하는데, 이 옵션은 윈도우즈를 오른쪽으로 많이 드래그를 해야 옵션을 찾을 수 있다. 그리고 link-layer를 802.11로 변경은 그냥 프로그램을 재실행하면 된다.

<img loading="lazy" class="alignnone wp-image-3804" src="http://res.cloudinary.com/openmicrolab/image/upload/v1480669330/WireShark_Monitor_mode_sp2hzp.png" width="1205" height="461" />