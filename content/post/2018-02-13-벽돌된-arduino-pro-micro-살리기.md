---
title: 벽돌된 Arduino Pro Micro 살리기
author: openmicrolab
type: post
date: 2018-02-13T11:40:34+00:00
url: /벽돌된-arduino-pro-micro-살리기/
categories:
  - Arduino
  - Tip
tags:
  - Arduino
  - Arduino Pro Micro

---
Sparkfun사의 <a href="https://www.sparkfun.com/products/12640" target="_blank" rel="noopener noreferrer">Arduino Pro Micro</a>는 ATmega32U4를 사용하고 USB CDC기능이 있다. 문제는 이 보드를 잘못 프로그래밍하면, 즉 아두이노에서 디바이스 선택을 잘못하거나, 5V 디바이스(16Mhz)인데 3.3V 디바이스(8Mhz)로 선택을 해서 프로그래밍을 하면 USB CDC포트가 사라져서 더 이상 프로그래밍을 할 수 없다.

### 해결 방법

Serial 포트를 연결해서 전원을 공급하고 보드의 RST와 GND를 연결했다 떼면, PC에서 시리얼 포트가 잡힌다. 이때 아두이노에서 제대로 된 세팅으로 다시 프로그래밍을 하면 된다.

<img loading="lazy" class="aligncenter" src="https://cdn.sparkfun.com/assets/6/d/3/4/a/523c8e23757b7fbe5f8b4584.png" width="423" height="309" />