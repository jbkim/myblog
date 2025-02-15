---
title: 전력소모를 줄이는 법 – Low Power System
author: openmicrolab
type: post
date: 2019-12-08T13:50:02+00:00
url: /전력소모를-줄이는-법-low-power-system/
categories:
  - Arduino
  - Hardware
  - Open Source Hardware
  - Infomation
  - Development
tags:
  - ATTiny
  - Battery
  - low power

---
배터리를 사용하는 제품은 필수적으로 전력소모를 줄여야 한다. 시스템에서 전력소모를 줄이기 위한 방법은 다음과 같다.

  * MCU의 동작 전압을 낮추고, 동작 Clock를 낮출 것
  * 리니어 레귤레이터 대신 스위칭 레귤레이터를 사용할 것
  * MCU내의 사용하지 않는 peripheral을 disable할 것: Timer, BOD, Watch Dog Timer, UART, ADC 등 특히 ADC나 UART
  * 전류를 센싱하는 저항이 있다면 이 저항의 크기를 높일 것
  * 코드에서 최대한 Sleep 모드를 사용할 것

참고로 Attiny45의 경우 어떤 응용에서 동작시 1.6mA정도까지 줄여봤다. 그리고 <a href="https://learn.sparkfun.com/tutorials/reducing-arduino-power-consumption/all" target="_blank" rel="noopener">이런 문서</a>도 참고하면 좋을 듯.