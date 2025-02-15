---
title: Nucleo 보드에서의 printf
author: openmicrolab
type: post
date: 2018-04-26T11:06:33+00:00
url: /nucleo-보드에서의-printf/
categories:
  - ARM
  - Infomation
  - Development
tags:
  - STM32
  - printf
  - nucleo

---
<img loading="lazy" class="alignnone wp-image-4290" src="https://res.cloudinary.com/openmicrolab/image/upload/v1524740338/IMG_6522_autbwr.jpg" width="361" height="361" />

임베디드 보드에서의 Hello World인 blink 테스트를 끝나면 printf를 찍기위해 UART를 연결하고 테스트를 한다. Nucleo 보드에서도 마찬가지로 작업을 하는데, 회로도를 보면 아두이노 핀 호환 컨넥터의 TX, RX핀에 연결이 되어있다. 하지만 자세히 회로도를 보면 default 연결은 이 핀들이 아니라 ST-Link칩에 연결이 되어 있다. 즉 UART2의 경우 ST-Link를 통해서 USB 컨넥터에 연결이되고 virtual COM port로 잡힌다. 매뉴얼에 보면 다음과 같이 나온다.

> The USART2 interface available on PA2 and PA3 of the STM32 microcontroller can be connected to ST-LINK MCU, ST morpho connector or to Arduino connector. The choice can be changed by setting the related solder bridges. By default the USART2 communication between the target STM32 and ST-LINK MCU is enabled, in order to support virtual COM port for MbedTM (SB13 and SB14 ON, SB62 and SB63 OFF). If the communication between the target STM32 PA2 (D1) or PA3 (D0) and shield or extension board is required, SB62 and SB63 should be ON, SB13 and SB14 should be OFF. In such case it is possible to connect another USART to ST-LINK MCU using flying wires between ST morpho connector and CN3.

따라서 아두이노 핀 호환핀에 연결을 하려면 점퍼 설정을 다시해야 하는데, printf를 위해서라면 virtual COM port를 사용하면 되니 그럴 필요는 없다.

<a href="https://github.com/jbkim/stm32_nucleo" target="_blank" rel="noopener noreferrer">관련 코드</a>