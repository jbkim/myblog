---
title: IEEE 1588 PTP (Precision Time Protocol)
author: openmicrolab
type: post
date: 2011-12-05T11:02:33+00:00
url: /ieee-1588-ptp-precision-time-protocol/
dsq_thread_id:
  - "1165747414"
categories:
  - Development
  - Network
tags:
  - IEEE1588
  - Precision Time Protocol
  - PTP

---
장비 내 각각의 부분별로 별도의 정확한 클럭이 존재하지만 ns에서 μs 사이에 발생하는 회로의 변화나 작은 차이도 금방 누적된다. 또한 네트워크 장비에서의 버퍼링등으로 인한 딜레이 및 연결로 인해 레이턴시 지연, 즉 ‘지터(Jitter)’ 또한 발생한다. 하지만 PTP를 추가함으로써 이러한 타이밍에 대한 보상을 함으로써 문제를 해결할 수 있다. 네트워크 구성과 장비에 따라 수십ns~수μs 내로 클럭을 동기화 할 수 있다.

이러한 기능이 필요한 한가지 예는 스마트 그리드 시스템이다. 즉 peak-hour 빌링 같은 기능을 위해 정확한 시간정보가 필요하다. PTP의 장점은  
-. 이미 네트워크 기능이 들어가 있는 장비에 PTP 프로토콜을 탑재함으로써 적은 비용으로 이런 기능의 구현이 가능하고,  
-. Multicast(UDP)를 이용해서 작은 bandwidth 만 요구된다.

PTP는 IEEE 1588 에 Precision Clock Synchronization for Networked Measurement and Control Systems 로 정의가 되어 있다. 이 표준은 디바이스가 네트워크상에서 가장 정밀하고 정확한 클럭을 활용할 수 있는 프로토콜을 제공한다.  
2 가지 버젼, PTP v1 IEEE 1588-2002, PTP v2 IEEE 1588-2008 이 있는데 하위 호환성은 없다.  
MAC/PHY칩의 경우 H/W&nbsp;적으로 IEEE 1588 time stamp 기능이 있는 칩이 있는데, 이런 칩의 경우 수 usec 내의 정확도를 보장하며, S/W만으로 구현할 경우 수 msec정도의 정확도가 가능하다.&nbsp;  
**참고로 PHY에서 IEEE 1555을 지원하는 것도 있다.** <A title="[http://www.national.com/pf/DP/DP83640.html#Overview]로 이동합니다." href="http://www.national.com/pf/DP/DP83640.html#Overview" target=_blank>**NI사의 DP83640**</A>**&nbsp;**

  


<P style="MARGIN: 0px">
  <a href="/images/1/cfile8.uf.133D703D4EDC981C0DC0A6.pdf" class="aligncenter" filename="DP83640.pdf"  filemime="application/pdf" />cfile8.uf.133D703D4EDC981C0DC0A6.pdf</a><br />
</P>

  


<P style="TEXT-ALIGN: center">
  <br />
</P>

  


<P style="TEXT-ALIGN: center">
  <STRONG>PTP Network</STRONG><img loading="lazy" src="/images/1/cfile1.uf.202734384EDC9F9B11336C.jpg" class="aligncenter" width="535" height="355" alt="" filename="PTP_network.jpg" filemime="image/jpeg" />
</P>

  


<P style="TEXT-ALIGN: center">
  <br />
</P>

  


<P style="TEXT-ALIGN: left">
  Master1이 문제가 있으면 Master2가 Grandmster가 된다.&nbsp;IED (Intelligent Electronice Device)
</p>

클럭 동기화를 위해 PTP는 time source인 마스터와 receiver인 슬레이브사이의 path delay를 정확히 측정을 해야하는데 아래&nbsp;다이아그램에 있는 것 처럼 메시지를 보내고 메시지를 수신함을써&nbsp;이것을 측정한다.

  


<P style="MARGIN: 0px">
  <img loading="lazy" src="/images/1/cfile30.uf.1479B13C4EDCA0692DFD57.gif" class="aligncenter" width="541" height="386" alt="" filename="PTP_NI.gif" filemime="image/jpeg" />
</P>

  


<P style="TEXT-ALIGN: left">
  1. Master가 Sync를 보내고 Slave는 이것을 수신한 시간을 기록. 82초<br /> 2. Master가 Follow up 패킷을 보낼때 데이터에 보낸 time stamp(100)을 넣어서 보냄.&nbsp;<br /> &nbsp;&nbsp; Slave는 100-82를 해서 옵셋을 보정함. 보정을 하니 Master가 103초일때 Slave는 101초이다. 즉 2초가 차이가 난다.<br /> 3. 이제 path delay만 보정하면 되는데, master to slave delay는 0 이다.<= 계산 방식은 위와 동일<br /> &nbsp;&nbsp;&nbsp;Slave to master delay는 4이다. 따라서 이것을 2로 나누면 +2초. 따라서 이 path delay 2초를 보정을 하면 master와&nbsp;<br /> &nbsp;&nbsp;&nbsp;slave간에 동기가 맞아진다.
</p>

구체적인 구현이나 테스트를 위해 보면 좋은 자료  
**IEEE 1588 precision time protocol demonstration for STM32F107 connectivity line microcontroller  
** 

  


<P style="MARGIN: 0px">
  <a href="/images/1/cfile29.uf.197FC53C4EDCA3E63148A9.pdf" class="aligncenter" filename="DM00030825.pdf"  filemime="application/pdf" />cfile29.uf.197FC53C4EDCA3E63148A9.pdf</a>
</P>

  


<P style="TEXT-ALIGN: left">
  <br /> <STRONG>참고</STRONG><br /> NI자료 <A title="[http://zone.ni.com/devzone/cda/tut/p/id/2822#toc4]로 이동합니다." href="http://zone.ni.com/devzone/cda/tut/p/id/2822#toc4" target=_blank>Introduction to Distributed Clock Synchronization and the IEEE 1588 Precision Time Protocol</A><br /> 시스코 자료 <A title="[http://www.cisco.com/en/US/docs/switches/connectedgrid/cgs2520/software/release/12_2_58_ey/configuration/cgs_2520_swcg.html#wp1988925]로 이동합니다." href="http://www.cisco.com/en/US/docs/switches/connectedgrid/cgs2520/software/release/12_2_58_ey/configuration/cgs_2520_swcg.html#wp1988925" target=_blank>Cisco CGS 2520 Switch Software Configuration Guide for IOS Release 12.2(58)EY</A>
</p>