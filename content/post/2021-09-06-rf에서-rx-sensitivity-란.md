---
title: RF에서 RX Sensitivity 란?
author: openmicrolab
type: post
date: 2021-09-06T04:43:17+00:00
url: /rf에서-rx-sensitivity-란/
cloudinary_transformations_terms:
  - 'a:3:{i:0;s:12:"category:286";i:1;s:13:"post_tag:1265";i:2;s:13:"post_tag:1317";}'
categories:
  - Wireless
tags:
  - RF
  - rf sensitivity

---
**RX Sensitivity**  
&#8211; 수신기가 감지할 수 있는 최소 신호 강도를 측정한 것. 즉 식별이 가능하고, 처리할 수 있는 가장 약한 신호를 알려준다.  
&#8211; RX Sensitivity는 dBm으로 표시  
&#8211; 신호의 미약한 정도를 나타내므로 신호의 전력 레벨이 낮을수록 좋다.  
&#8211; 예를 들어 -90dBm의 수신기 감도는 -80dBm보다 낫다. 즉, -90dBm 수신기가 더 민감하고 더 낮은 전력 신호를 해석할 수 있음을 의미한다.

**Receiver Sensitivity Requirements for modules:**  
&#8211; LoRa: up to -130 dBm  
&#8211; Cellular: up to -120 dBm  
&#8211; Bluetooth: -70 dBm to -100 dBm  
&#8211; ZigBee: -85 to -92 dBm  
&#8211; Wi-Fi: -40 dBm to -80 dBm

**TX Power**  
TX Power는 worst-case에서도 적어도 이 정도의 전송 전력을 보장한다는 수치이다.