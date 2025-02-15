---
title: Yaler.net relay service
author: openmicrolab
type: post
date: 2015-10-02T13:28:48+00:00
url: /yaler-net-relay-service/
categories:
  - IoT
  - Arduino
  - Open Source Hardware
  - Service
tags:
  - Arduino
  - Yaler.net
  - Yaler.net relay service
  - IFTTT

---
네트워크 기능이 내장된 임베디드 디바이스의 경우 내부 네트워크에서 외부로 접속은 쉽지만, 반대로 외부에서 이 디바이스로의 접근은 방화벽등이 있으면 쉽지않고, 공유기에서 NAT, 포트포워딩 등의 기능을 사용해야 해서 일반사용자들은 이용이 어렵다.

**Yaler.net relay service**  
<a href="https://yaler.net/" target="_blank">Yaler.net</a>은 이런 문제점을 해결해 줄 수 있는 서비스인데 아래 그림을 보면 동작이 쉽게 이해가 되며, <a href="https://yaler.net/help" target="_blank">튜토리얼 문서</a>를 보면 Arduino, Beaglebone, Raspberry Pi&#8230; 등의 유명한 보드들의 셋업가이드도 자세하게 나와있다.

[<img loading="lazy" class="aligncenter wp-image-3429 size-full" src="/images/2015/10/Yaler_net_-_access_devices_from_the_Web.jpg" alt="Yaler_net_-_access_devices_from_the_Web" width="531" height="508" srcset="/images/2015/10/Yaler_net_-_access_devices_from_the_Web.jpg 531w, /images/2015/10/Yaler_net_-_access_devices_from_the_Web-300x287.jpg 300w" sizes="(max-width: 531px) 100vw, 531px" />][1]

**비용**  
비용은 회원가입을 하면 30일 무료이고, 최저 10CHF (스위스 프랑)이니 약 10불정도이니 비싸지 않다.

**테스트**  
회원가입을 하면 자신의 계정에 다음과 같이 Relay Host, Relay Domain, Secret Key가 생성이 된다.

[<img loading="lazy" class="aligncenter  wp-image-3430" src="/images/2015/10/Yaler_net_-_Account.jpg" alt="Yaler_net_-_Account" width="801" height="64" srcset="/images/2015/10/Yaler_net_-_Account.jpg 951w, /images/2015/10/Yaler_net_-_Account-300x24.jpg 300w" sizes="(max-width: 801px) 100vw, 801px" />][2]

동작이 되는지 확인을 위해 curl을 이용해 테스트를 하면&#8230;

> $ curl -vX POST gsiot-sqqm-gym8.try.yaler.net/

다음과 같이 HTTP/1.1 504가 뜨는데 이것은 보드가 온라인이 아니거나 또는 설정이 제대로 되어 있지 않아서 이렇게 응답을 하는 것이고, 만약 제대로 되면 HTTP/1.1 200 OK로 응답을 한다.

[<img loading="lazy" class="aligncenter wp-image-3431 size-full" src="/images/2015/10/yaler_cmdline.jpg" alt="yaler_cmdline" width="642" height="233" srcset="/images/2015/10/yaler_cmdline.jpg 642w, /images/2015/10/yaler_cmdline-300x109.jpg 300w" sizes="(max-width: 642px) 100vw, 642px" />][3]

**응용**  
Instructables에  Arduino와 Yaler, IFTTT를 사용한 <a href="http://www.instructables.com/id/IoT-Gauge-with-Arduino-Yaler-IFTTT/" target="_blank">IoT Gauge with Arduino, Yaler & IFTTT</a> 프로젝트가 있는데, 여기서는 IFTTT의 <a href="https://ifttt.com/maker" target="_blank">Maker 채널</a> 을 사용하고 &#8220;Make a web request&#8221;에  Yaler 서비스 정보를 기입해서 폰의 위치정보에따라서 디바이스(Arduino Uno, Arduino Yun) 가 반응하는 꽤 흥미로운 프로젝트를 만들었으니 참고해 보면 Yaler, IFTTT, Maker Channel을 이해하는데 도움이 된다.

<img loading="lazy" class="aligncenter" src="http://cdn.instructables.com/FMO/J4IT/ICEMXRME/FMOJ4ITICEMXRME.MEDIUM.jpg" alt="IoT Gauge with Arduino, Yaler & IFTTT" width="491" height="368" /> 

**괜찮은 서비스**  
<a href="https://pushover.net/" target="_blank">Pushover</a>: 안드로이드, 아이폰에 알림을 띄워주는 서비스이며 <a href="https://ifttt.com/pushover" target="_blank">IFTTT에도 채널</a>로 등록이 되어 있다.

 [1]: /images/2015/10/Yaler_net_-_access_devices_from_the_Web.jpg
 [2]: /images/2015/10/Yaler_net_-_Account.jpg
 [3]: /images/2015/10/yaler_cmdline.jpg