---
title: Arduino Ethernet 라이브러리 업데이트
author: openmicrolab
type: post
date: 2014-03-01T09:26:21+00:00
url: /arduino-ethernet-라이브러리-업데이트/
dsq_thread_id:
  - "2339646951"
categories:
  - Open Source Hardware
  - Development
  - Network
  - Wiznet
tags:
  - Ethernet
  - Arduino
  - W5100
  - W5200
  - W5500

---
WZnet 칩 W5100, W5200과 W5500을 지원하는 통합 아두이노 라이브러리인 <a href="https://github.com/Wiznet/WIZ_Ethernet_Library" target="_blank">Arduino Ethernet 라이브러리</a>를 업데이트 했다. 기존 코드에서 달라진 점은 다음과 같다.

  * Arduino IDE 1.5.x 지원 : Arduino Due를 지원하기 위함.
  * Due용  SPI 드라이버 추가
  * W5200및 W5500의 경우 SPI드라이버 속도를 높였다. 무려 42Mhz까지 지원
  * w5100::read_data함수의 파라미터의 형 변경
  * flush() 함수 추가

Arduino IDE 1.5.xx를 지원하기 위해서는

  * 32비트 SAM용 SPI 드라이버가 추가 되야한다.
  * IDE 1.5.x의 폴더 구조가 바뀌어서 헤더파일 include가 변경된다.아래 그림 참고&#8230;  예를 들면 #include &#8220;w5100.h&#8221;가 #include &#8220;utility/ w5100.h&#8221; 이런 식으로&#8230;

[<img loading="lazy" class="alignnone  wp-image-2890" alt="Arduino_Folder" src="/images/2014/03/Arduino_Folder-826x1024.png" width="578" height="717" srcset="/images/2014/03/Arduino_Folder-826x1024.png 826w, /images/2014/03/Arduino_Folder-242x300.png 242w, /images/2014/03/Arduino_Folder.png 831w" sizes="(max-width: 578px) 100vw, 578px" />][1]

  * AVR코드와의 구별은 #if defined (ARDUINO\_ARCH\_AVR)로 한다.

### W5500 SPI

[<img loading="lazy" class="alignnone size-full wp-image-2891" alt="W5500_SPI" src="/images/2014/03/W5500_SPI.png" width="678" height="655" srcset="/images/2014/03/W5500_SPI.png 678w, /images/2014/03/W5500_SPI-300x289.png 300w" sizes="(max-width: 678px) 100vw, 678px" />][2]

데이터 시트에는 이론상 80Mhz까지 가능하다고 나오지만 실제로는 33Mhz 정도가 최대 SPI clock으로 명기해 놓고 있다. 그리고 Atmel SAM에서  SPI clock은 다음과 같이 결정된다. 즉 메인 클럭을 분주해서 사용을 하는데, 아두이노에서는 84Mhz를 메인으로 사용하므로 14Mhz, 28Mhz, 42Mhz, 84Mhz가 설정이 가능하다.

[<img loading="lazy" class="alignnone  wp-image-2892" alt="SAM_SPI" src="/images/2014/03/SAM_SPI.png" width="718" height="237" srcset="/images/2014/03/SAM_SPI.png 998w, /images/2014/03/SAM_SPI-300x98.png 300w" sizes="(max-width: 718px) 100vw, 718px" />][3]

&nbsp;

아두이노 코드에서는 다음과 같이 클럭을 분주해서 42Mhz가 가능하다. 1로 분주하면 84Mhz 인데, 칩에서는 80Mhz까지만 지원하므로 84Mhz는 지원이 안된다. 42에서 84는 갭이 크다&#8230;

참고로 아두이노에서 W5100의 SPI는 4Mhz로 설정이 되어 있으니, 거의 10배 이상이 빨라짐~~

 [1]: /images/2014/03/Arduino_Folder.png
 [2]: /images/2014/03/W5500_SPI.png
 [3]: /images/2014/03/SAM_SPI.png