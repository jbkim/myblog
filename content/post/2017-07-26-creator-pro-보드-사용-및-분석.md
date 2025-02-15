---
title: CREATOR Pro 보드 사용 및 분석
author: openmicrolab
type: post
date: 2017-07-26T07:09:23+00:00
url: /creator-pro-보드-사용-및-분석/
categories:
  - IoT
  - Wireless
  - mbed
  - Open Source Hardware
tags:
  - WIFI
  - Arduino
  - mbed
  - CREATOR Pro
  - RAK473
  - RTL8711
  - RTL8710

---
<a href="http://www.rakwireless.com/en/" target="_blank" rel="noopener noreferrer">Rak Wireless</a>사의 CREATOR Pro 보드는 Arduino Uno의 폼펙터를 가지며, RAK473 WiFi 모듈을 사용하고 NXP사의 LPC11U35를 사용해서 mbed에서도 프로그래밍이 가능하고, Arduino에서도 프로그래밍이 가능하다. <a href="http://wiki.rakwireless.com/doku.php?id=wisnode_series:creator_pro" target="_blank" rel="noopener noreferrer">WiKi</a>에 나온 이 제품의 정보는 다음과 같은데, Realtek사의 <a href="https://www.amebaiot.com/en/" target="_blank" rel="noopener noreferrer">Ameba RTL8710보드</a>와 거의 동일하다.

> CREATOR is a programmable platform for developing all kind of IoT applications. CREATOR is equiped with various peripheral interfaces, including Wifi, GPIO, I2C, UART, PWM, ADC. Through these interfaces, CREATOR can connect with electronic components such as LED, switches, manometer, hygrometer, PM2.5 dust sensors etc.  
> The collected data can be uploaded via WiFi, and be utilized by applications on smart devices to realize IoT implementation.  
> CREATOR and Arduino Uno have similar size, and the pins on CREATOR are compatible with Arduino Uno. CREATOR uses Micro USB to supply power, which is common in many smart devices.  
> Currently, CREATOR currently supports Windows XP/7/8 32 and 64 bits and MAC OS operating systems. In this example, please use Arduino IDE with version 1.6.7 or later.

<img class="mediacenter aligncenter" src="http://wiki.rakwireless.com/lib/exe/fetch.php?w=450&tok=46124d&media=creator_pro1.png" alt="" width="450" /> 

**LPC11U35의 역할**

  * CMSYS-DAP가 내장
  * RAK473를 프로그래밍 및 디버깅이 가능하게 함
  * CMSYS-DAP 펌웨어는 JTAG을 통해서 업로드하고, 이후에는 CRP-DISABLED에 파일을 Copy하면 된다. **문제는 Mac에서 파일을 카피하면 안되고 윈도우즈에서만 된다.** <a href="https://www.amebaiot.com/en/change-dap-firmware/" target="_blank" rel="noopener noreferrer">관련자료</a>
  * Tindie에서 $15에 판매하는 같은 기능을 갖는 <a href="https://www.tindie.com/products/microwavemont/ameba-rtl8710-programmer-for-arduino-ide/" target="_blank" rel="noopener noreferrer">외장형 보드</a>

**RAK473**

  * Realtek사의 <a href="http://www.realtek.com/products/productsView.aspx?Langid=1&PNid=33&PFid=45&Level=4&Conn=3&ProdID=363" target="_blank" rel="noopener noreferrer">RTL8711AM</a>을 사용함
  * AT command로 동작함
  * <a href="http://wiki.rakwireless.com/doku.php?id=iot-product:rak473" target="_blank" rel="noopener noreferrer">구체적인 정보</a>
  * <a href="https://ko.aliexpress.com/wholesale?catId=0&initiative_id=SB_20170725030857&SearchText=rtl8710" target="_blank" rel="noopener noreferrer">유사한 제품들</a>

![][1] 

**Rak 홈페이지의 자료 및 Github의 자료**

  * <a href="http://www.rakwireless.com/en/download/Wis%20Creator%20Pro/Software%20Development" target="_blank" rel="noopener noreferrer">Software Development</a>
  * <a href="http://www.rakwireless.com/en/download/Wis%20Creator%20Pro/Hardware%20Design" target="_blank" rel="noopener noreferrer">Hardware Schematics</a>
  * <a href="http://www.rakwireless.com/en/download/Wis%20Creator%20Pro/Tools" target="_blank" rel="noopener noreferrer">Tool</a>
  * <a href="https://github.com/RAKWireless/CREATOR-Arduino-SDK" target="_blank" rel="noopener noreferrer">CREATOR-Arduino-SDK</a>
  * <a href="https://github.com/RAKWireless/CREATOR-Standard-SDK" target="_blank" rel="noopener noreferrer">CREATOR-Standard-SDK</a>

**아두이노 개발 환경에서 사용법**

  * <a href="http://docs.rakwireless.com/en/Wis%20Creator%20Pro/Software%20Development/CREATOR%20pro%20Development%20environment%20.pdf" target="_blank" rel="noopener noreferrer">CREATOR pro :[RAK47X-RTL8711] Development environment</a>
  * <a href="https://github.com/jbkim/CreatorPro/blob/master/CREATOR%20Development%20Environment%20for%20MAC_KOR.pdf" target="_blank" rel="noopener noreferrer">이 자료를 한글로 번역한 자료</a>

**추가적으로 함께 보면 좋은 자료**

  * <a href="https://www.rtl8710forum.com/viewtopic.php?f=3&t=5" target="_blank" rel="noopener noreferrer">https://www.rtl8710forum.com/viewtopic.php?f=3&t=5</a>
  * <a href="http://www.cnx-software.com/2016/08/01/development-resources-for-realtek-ameba-rtl8710-rtl8711-and-rtl8195-wifi-socs/" target="_blank" rel="noopener noreferrer">http://www.cnx-software.com/2016/08/01/development-resources-for-realtek-ameba-rtl8710-rtl8711-and-rtl8195-wifi-socs/</a>

 [1]: http://www.cnx-software.com/wp-content/uploads/2016/08/Realtek_Ameba_Comparison_Table.png