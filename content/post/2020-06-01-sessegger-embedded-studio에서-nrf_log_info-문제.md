---
title: SES(Segger Embedded Studio)에서 NRF_LOG_INFO 문제
author: openmicrolab
type: post
date: 2020-06-01T09:14:20+00:00
url: /sessegger-embedded-studio에서-nrf_log_info-문제/
categories:
  - Bluetooth
  - Infomation
  - Development
tags:
  - BLE
  - nordic
  - SES

---
SES환경에서 NRF\_LOG\_INFO(&#8220;Blinky example started!!!&#8221;)와 같은 같은 디버그 문구가 Debug Terminal에 보이지 않는 이슈 해결 방법

sdk_config.h 파일에서 다음과 같이 기존에 1로 설정되어 있던 값을 0 으로 수정한다.

```#define NRF_LOG_DEFERRED 0`  
`#define NRF_FPRINTF_FLAG_AUTOMATIC_CR_ON_LF_ENABLED 0`

`#define NRF_LOG_BACKEND_RTT_ENABLED 1`  
`#define NRF_LOG_ENABLED 1`  
이 설정도 되어 있어야 함.

그런데 다음 설정은 0으로 되야 함  
`#define NRF_LOG_BACKEND_UART_ENABLED 0`

그리고 보드가 바뀌면 아래 핀 설정도 같이 해야 함.  
`#define NRF_LOG_BACKEND_UART_TX_PIN 6`