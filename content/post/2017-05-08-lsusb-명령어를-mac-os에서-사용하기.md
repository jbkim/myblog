---
title: lsusb 명령어를 Mac OS에서 사용하기
author: openmicrolab
type: post
date: 2017-05-08T01:58:33+00:00
url: /lsusb-명령어를-mac-os에서-사용하기/
categories:
  - Development
tags:
  - USB
  - lsusb
  - usb vid
  - usb pid

---
리눅스에 있는 lsusb를 사용할 수 있는 프로그램: <https://github.com/jlhonora/lsusb>

다음과 같이 brew로 인스톨한다.

> brew update && brew tap jlhonora/lsusb && brew install lsusb 

다음과 같은 옵션으로 사용 가능.

    List USB devices
      -v  Increase verbosity (show output of "system_profiler SPUSBDataType")
      -s  [[bus]:][devnum]
           Show only devices with specified device and/or
           bus numbers (in decimal)
      -d  [vendor]:[product]
           Show only devices with the specified vendor and
           product ID numbers (in hexadecimal)
      -p  Display manufacturer names in parentheses
      -t  Dump the physical USB device hierarchy as a tree
      -V  Show version of program
      -h  Show usage and help