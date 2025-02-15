---
title: PlatformIO, Arduino에서의 핀매핑 정보
author: openmicrolab
type: post
date: 2021-02-18T08:23:52+00:00
url: /platformio-arduino에서의-핀매핑-정보/
featured_image: /wp-content/uploads/2021/02/platformIO-100x100.png
categories:
  - Arduino
  - Open Source Hardware
  - Infomation
  - Development
tags:
  - Arduino
  - platformIO
  - 아두이노핀매핑

---
펌웨어 개발을 할때 MCU의 I/O핀을 맵핑해서 사용을 하게 된다. 아두이노의 경우에는 실제 HW 핀 매핑을 MCU 벤더에서 제공하는 것 처럼 low level로 access하지 않고, 보드의 실크에 적혀있는 핀 번호로 access할 수 있도록 추상화를 해 놓았다. 실제로 핀 매핑이 어떻게 되는지 보려면 맥의 경우 $HOME/라이브러리/Arduino15/packages 아래에 각 플랫폼 별로 되어 있는 폴더를 확인해 봐야 한다. 예를 들면 adafruit의 경우 /packages/adafruit/hardware/nrf52/0.21.0/variants/feather\_nrf52840\_express/variant.h파일과 variant.cpp 파일을 확인해 보면 된다.

PlatformIO도 아두이노와 마찬가지로 VSCode에 설치를 하면 맥에서는 $HOME/.platformio/packages 폴더 아래에 각각의 프레임워크에서 사용하는 bootloader, library들이 설치가 되어 있다.

[<img loading="lazy" class="aligncenter wp-image-4714 size-large" src="/images/2021/02/platformIO-1024x293.png" alt="" width="1024" height="293" srcset="/images/2021/02/platformIO-1024x293.png 1024w, /images/2021/02/platformIO-300x86.png 300w, /images/2021/02/platformIO-768x220.png 768w, /images/2021/02/platformIO.png 1223w" sizes="(max-width: 1024px) 100vw, 1024px" />][1]

 [1]: /images/2021/02/platformIO.png