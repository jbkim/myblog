---
title: Beyond connectivity, toward value – IoT(IoE), 비즈니스 미래 지형을 바꾸다
author: openmicrolab
type: post
date: 2014-03-08T14:22:54+00:00
url: /beyond-connectivity-toward-value-iotioe-비즈니스-미래-지형을-바꾸다/
dsq_thread_id:
  - "2388417738"
categories:
  - IoT
tags:
  - IOT
  - MQTT
  - paho
  - JavaME Embedded for IoE Platform
  - Orion Board
  - Gateway solution(One Box)
  - AllJoyn

---
지난 3월 5일 참석한 컨퍼런스

[<img loading="lazy" class="alignnone size-full wp-image-2912" alt="iot_semina" src="/images/2014/03/iot_semina.jpeg" width="677" height="645" srcset="/images/2014/03/iot_semina.jpeg 677w, /images/2014/03/iot_semina-300x285.jpeg 300w" sizes="(max-width: 677px) 100vw, 677px" />][1]

&nbsp;

### 발표의 내용을 요약하면

  * IoT(Internet of Things), IoE(Internet of Everything)등으로 각 업체마다 추정치는 다르나 향후 널리 확산될 것으로 예상
  * 수량은 PC, 태블릿, 스마트폰의 수치를 합한 것의 2배로 추정, 여기에 Smart TV, Wearable의 수치도 IoT와 비등한 수준
  * 가트너에서 발표한 <a href="http://www.gartner.com/newsroom/id/2575515" target="_blank">Hype Cycle 곡선</a>
  * IoT에서의 보안의 이슈: <a href="http://www.telegraph.co.uk/technology/internet-security/10579677/More-than-750000-spam-emails-sent-from-fridges-and-TVs.html" target="_blank">냉장고가 스팸메일 보낸 뉴스</a>, <a href="http://arstechnica.com/security/2014/02/password-leak-in-wemo-devices-makes-home-appliances-susceptible-to-hijacks/" target="_blank">밸킨의 Wemo 해킹 뉴스</a>
  * <span style="line-height: 1.5em;">국내 통신사들: KT, LG-Uplus, SK 텔레콤등이 실제적인 서비스( Biz Case)를 발표</span>
  * <span style="line-height: 1.5em;">매직에코: LimiSmart라는 램프에 IoT기능을 넣은 제품으로 인디고고에서 프로젝트 진행중 &#8211; S/W 저작 도구</span>
  * <span style="line-height: 1.5em;">daliworks : IoT cloud platform 서비스 제공(SensorJS), IoT 센서 게이트 웨이(비글본, 라즈베리 파이)</span>

### <span style="font-size: 1.17em;">글로벌 벤더들의 IoT주도권을 위한 경쟁</span>

  * <span style="line-height: 1.5em;">오라클: </span><a style="line-height: 1.5em;" href="http://www.oracle.com/technetwork/java/javame/index.html" target="_blank">JavaME Embedded for IoE Platform</a><span style="line-height: 1.5em;"> 퀄컴의 Orion Board에서 채택, Gateway solution(</span><a style="line-height: 1.5em;" href="https://community.freescale.com/community/the-embedded-beat/blog/2013/09/23/what-is-the-new-freescale-oracle-partnership-around-one-box-platform-all-about-part-1" target="_blank">One Box</a><span style="line-height: 1.5em;">)</span>
  * 퀄컴: AllJoyn &#8211;  P2P기반, 지금은 오픈 소스화 되어 Linux foundation 에서 유지.
  * <a style="line-height: 1.5em;" href="/images/2014/03/alljoyn.jpeg"><img loading="lazy" class="alignnone  wp-image-2913" alt="alljoyn" src="/images/2014/03/alljoyn.jpeg" width="578" height="311" srcset="/images/2014/03/alljoyn.jpeg 964w, /images/2014/03/alljoyn-300x161.jpeg 300w" sizes="(max-width: 578px) 100vw, 578px" /></a>
  * <span style="line-height: 1.5em;">IBM: </span><a style="line-height: 1.5em;" href="http://mqtt.org/" target="_blank">MQTT</a> <span style="line-height: 1.5em;">&#8211; IoT  메시징 프로토콜, </span><a style="line-height: 1.5em;" href="http://www.eclipse.org/paho/" target="_blank">paho</a>
  * MS의 IoT에 대한 정의
  * <a style="line-height: 1.5em;" href="/images/2014/03/ms_iot.jpeg"><img loading="lazy" class="alignnone size-full wp-image-2914" alt="ms_iot" src="/images/2014/03/ms_iot.jpeg" width="484" height="242" srcset="/images/2014/03/ms_iot.jpeg 484w, /images/2014/03/ms_iot-300x150.jpeg 300w" sizes="(max-width: 484px) 100vw, 484px" /></a>

###  My Insight

  * IoT 단말은 무선
  * IoT 게이트웨이는 상위 서비스와 연계하기 위해 보안 및 OS가 필요하며, 현재는 무겁고 비싸지만 가격은 점차내려갈 것고 모든 무선인터페이스(Zigbee, BT, WiFi)를 포함하는 형태가 될 것이다. 특히 가정내 IoT 게이트 웨이의 경우는 더더욱&#8230;
  * 서비스에 연계되지 않은 단말은 중국과의 가격경쟁으로 살아남기 힘들다.

위 세미나와 관련된 내용: <a href="http://www.businessinsider.com/the-internet-of-everything-2014-slide-deck-sai-2014-2#-1" target="_blank">BI에서 발표한 자료</a>

 [1]: /images/2014/03/iot_semina.jpeg