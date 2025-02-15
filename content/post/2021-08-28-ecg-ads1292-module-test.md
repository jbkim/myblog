---
title: ECG – ADS1292 module test
author: openmicrolab
type: post
date: 2021-08-28T08:24:53+00:00
url: /ecg-ads1292-module-test/
cloudinary_transformations_terms:
  - 'a:3:{i:0;s:13:"post_tag:1311";i:1;s:13:"post_tag:1312";i:2;s:13:"post_tag:1313";}'
categories:
  - Uncategorized
tags:
  - ecg
  - wio terminal
  - ads1292

---
심장의 ECG신호를 측정할 수 있는 ADS1292모듈을 테스트해 봤다. 먼저 Arduino Uno를 가지고 테스트를 해서 신호가 제대로 나오는 지를 확인한다.

[<img loading="lazy" class="wp-image-4772 aligncenter" src="/images/2021/08/arduinoUno_ecg-300x300.jpg" alt="" width="353" height="353" srcset="/images/2021/08/arduinoUno_ecg-300x300.jpg 300w, /images/2021/08/arduinoUno_ecg-1024x1024.jpg 1024w, /images/2021/08/arduinoUno_ecg-150x150.jpg 150w, /images/2021/08/arduinoUno_ecg-768x768.jpg 768w, /images/2021/08/arduinoUno_ecg-1536x1536.jpg 1536w, /images/2021/08/arduinoUno_ecg-2048x2048.jpg 2048w, /images/2021/08/arduinoUno_ecg-100x100.jpg 100w, /images/2021/08/arduinoUno_ecg-336x336.jpg 336w" sizes="(max-width: 353px) 100vw, 353px" />  
][1] 

[<img loading="lazy" class="wp-image-4773 aligncenter" src="/images/2021/08/ecg_uno-300x132.png" alt="" width="505" height="222" srcset="/images/2021/08/ecg_uno-300x132.png 300w, /images/2021/08/ecg_uno-1024x452.png 1024w, /images/2021/08/ecg_uno-768x339.png 768w, /images/2021/08/ecg_uno-1536x678.png 1536w, /images/2021/08/ecg_uno-2048x904.png 2048w" sizes="(max-width: 505px) 100vw, 505px" />][2]

신호의 출력값은 Arduino Plotter를 이용해서 확인을 한다. 다음 스텝은 이 값을

1) SeeedStudio 의 Wio Terminal같은 디스플레이가 있는 디바이스에서 진행을 하거나,

2) 출력값을 BLE를 이용해 웹에서 Plot을 하거나

3) WiFi를 이용해서 서버에서 데이터를 받아서 디스플레이를 하는 3가지 형태로 진행을 할 예정~

 [1]: /images/2021/08/arduinoUno_ecg.jpg
 [2]: /images/2021/08/ecg_uno.png