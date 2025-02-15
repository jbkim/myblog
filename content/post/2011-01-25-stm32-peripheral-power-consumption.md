---
title: STM32 Peripheral power consumption
author: openmicrolab
type: post
date: 2011-01-25T07:01:00+00:00
url: /stm32-peripheral-power-consumption/
categories:
  - Infomation
  - Development
tags:
  - STM32
  - power consumption
  - 전류소비

---
<img loading="lazy" src="/images/1/cfile4.uf.1960E4584D3E7496131E66.jpg" class="aligncenter" width="502" height="680" alt="" filename="STM32_power_consumption.jpg" filemime="image/jpeg" />위 표에서 볼 수 있듯이 APB1은 HCLK을 2분주해서 사용을 하고 APB2는 HCLK를 그대로 사용을 합니다.  
따라서 APB2에 연결된 페리페럴이 더 빠르게 동작하며 전류 소비도 더 큽니다.  
ADC는 역시 아날로그 파트라 전류 소비가 크군요.