---
title: Transformer없이 이더넷 구현하기
author: openmicrolab
type: post
date: 2013-11-20T11:14:11+00:00
url: /transformer없이-이더넷-구현하기/
dsq_thread_id:
  - "1988731730"
categories:
  - Network
tags:
  - Ethernet
  - Ethernet PHY

---
일반적으로 이더넷 응용에서는 PHY의 출력단에 트랜스포머가 필요하다. 하지만 길이가 짧은 경우나 특별한 응용의 경우 트랜스포머를 사용하지 않고 구현이 가능하다. 이 때는 TX+-, RX+- 신호에 DC 커플링 캐패시터 33nF를 연결을 한다.

[wpdm_file id=6]

사실 이 내용보다는 IEEE802.3에서 요구하는 PHY signal의 형태가 다른 문서에서는 볼 수 없어서 귀중한 자료&#8230;

[<img loading="lazy" class="alignnone size-full wp-image-2703" alt="Phy_Signal" src="/images/2013/11/Phy_Signal.png" width="631" height="726" srcset="/images/2013/11/Phy_Signal.png 631w, /images/2013/11/Phy_Signal-260x300.png 260w" sizes="(max-width: 631px) 100vw, 631px" />][1]

 [1]: /images/2013/11/Phy_Signal.png