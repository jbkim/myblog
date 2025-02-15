---
title: Cura 코드 수정 – Silab 디바이스 인식
author: openmicrolab
type: post
date: 2016-06-13T08:15:32+00:00
url: /cura-코드-수정-silab-usb-serial-디바이스-인식/
categories:
  - 3D Printer
  - Development
tags:
  - 3d printer
  - Cura
  - avrdude
  - firmware update
  - auto

---
기존 코드는 USB ACM디바이스들을 list에 넣어서 인식하도록 했는데, Silab 디바이스도 추가되도록 macineCOM.py 파일의 serialList 함수 수정.