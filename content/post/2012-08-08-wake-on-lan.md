---
title: Wake on LAN
author: openmicrolab
type: post
date: 2012-08-08T23:10:50+00:00
url: /wake-on-lan/
dsq_thread_id:
  - "1153975740"
categories:
  - Development
  - Network
tags:
  - Ethernet
  - wireshark
  - W5200
  - Wake On Lan
  - WOL

---
Wake on LAN은 네트워크 패킷(매직 패킷)으로 컴퓨터를 켜거나, 깨우는 기능을 하는&nbsp;AMD와 HP에서 만든&nbsp;표준이다.

요즘 PC들은 전원을 꺼도 이더넷 잭에 연결된 LED가 깜박이는 것을 볼 수 있는데, 즉 LAN은 패킷을 받을 수 있는 모드에 있다.&nbsp;

</p> 

<p style="text-align: center; ">
  AMD의 White paper
</p></p> 

<p style="text-align: center; ">
  <a href="/images/1/cfile26.uf.1225CD3F5022E8BF13F2F0.pdf" class="aligncenter" filename="20213.pdf" filemime="application/pdf" />cfile26.uf.1225CD3F5022E8BF13F2F0.pdf</a>
</p>

<p style="text-align: center; ">
</p>



**매직 패킷의 구성**

매직 패킷은 2가 있는데,&nbsp;**ether-wake**와 **UDP**상에서 구현하는 패킷이 있다. 대부분의 PC 프로그램이 보내는 패킷은 후자이다.



아래 내용은 ether-wake패킷의 구성이다. 출처)&nbsp;<a href="http://wiki.wireshark.org/WakeOnLAN" target="_blank" class="tx-link">http://wiki.wireshark.org/WakeOnLAN</a>

이 사이트에서 관련 패킷 샘플도 다운로드 가능하다.</p> 

<table style="color: rgb(0, 0, 0); font-family: Arial, Helvetica, sans-serif; font-size: 13px; line-height: normal; margin: 0.5em 0px 0px 0.5em; border-collapse: collapse; text-align: left; width: 460px; height: 55px; ">
  <tr>
    <td style="padding: 0.25em 0.5em; border: 1pt solid rgb(173, 185, 204); vertical-align: top; text-align: center; background-color: rgb(255, 153, 102); height: 27px; ">
      <p class="line891" style="font-size: 13px; color: rgb(0, 0, 0); line-height: 17px; margin-right: 0px; margin-left: 0px; padding: 0px; ">
        <strong>Synchronization Stream</strong>
      </p>
    </td>
    
    <td style="padding: 0.25em 0.5em; border: 1pt solid rgb(173, 185, 204); text-align: center; vertical-align: top; background-color: rgb(102, 255, 102); height: 27px; ">
      <p class="line891" style="font-size: 13px; color: rgb(0, 0, 0); line-height: 17px; margin-right: 0px; margin-left: 0px; padding: 0px; ">
        <strong>Target MAC</strong>
      </p>
    </td>
    
    <td style="padding: 0.25em 0.5em; border: 1pt solid rgb(173, 185, 204); text-align: center; vertical-align: top; background-color: rgb(255, 255, 102); height: 27px; ">
      <p class="line891" style="font-size: 13px; color: rgb(0, 0, 0); line-height: 17px; margin-right: 0px; margin-left: 0px; padding: 0px; ">
        <strong>Password (optional)</strong>
      </p>
    </td>
  </tr>
  
  <tr>
    <td style="padding: 0.25em 0.5em; border: 1pt solid rgb(173, 185, 204); text-align: center; vertical-align: top; background-color: rgb(255, 153, 102); ">
      <span class="anchor" id="line-14" style="font-size: 13px; color: rgb(0, 0, 0); line-height: 17px; "></span></p> 
      
      <p class="line862" style="font-size: 13px; color: rgb(0, 0, 0); line-height: 17px; margin-right: 0px; margin-left: 0px; padding: 0px; ">
        6
      </p>
    </td>
    
    <td style="padding: 0.25em 0.5em; border: 1pt solid rgb(173, 185, 204); text-align: center; vertical-align: top; background-color: rgb(102, 255, 102); ">
      <p class="line862" style="font-size: 13px; color: rgb(0, 0, 0); line-height: 17px; margin-right: 0px; margin-left: 0px; padding: 0px; ">
        96
      </p>
    </td>
    
    <td style="padding: 0.25em 0.5em; border: 1pt solid rgb(173, 185, 204); text-align: center; vertical-align: top; background-color: rgb(255, 255, 102); ">
      <p class="line862" style="font-size: 13px; color: rgb(0, 0, 0); line-height: 17px; margin-right: 0px; margin-left: 0px; padding: 0px; ">
        0, 4 or 6
      </p>
    </td>
  </tr>
</table>

<p style="color: rgb(51, 51, 51); font-family: 돋움; font-size: 12px; line-height: 18px; ">
  -. Synchronization Stream : FF FF FF FF FF FF
</p>

<p style="color: rgb(51, 51, 51); font-family: 돋움; font-size: 12px; line-height: 18px; ">
  -. Target MAC: 깨울 상대의 맥 어드레스
</p>

<p style="color: rgb(51, 51, 51); font-family: 돋움; font-size: 12px; line-height: 18px; ">
  -. Password: 옵션
</p>

<p style="color: rgb(51, 51, 51); font-family: 돋움; font-size: 12px; line-height: 18px; ">
  즉 옵션이 없고 맥 어드레스가 01:02:03:04:05:06 이면 패킷의 형태는 다음과 같다.
</p>

<p style="color: rgb(51, 51, 51); font-family: 돋움; font-size: 12px; line-height: 18px; ">
  <pre style="color: rgb(0, 0, 0); line-height: normal; "><p>
  FFFFFFFFFFFF010203040506010203040506010203040506010203040506
  010203040506010203040506010203040506010203040506010203040506
  010203040506010203040506010203040506010203040506010203040506
  010203040506010203040506
</p>

<p>
  <br />
</p>

<p>
  <img loading="lazy" src="/images/1/cfile27.uf.1326484A5022FD61053383.png" class="aligncenter" width="683" height="18" filename="wol.png" filemime="image/jpeg" style="color: rgb(51, 51, 51); font-family: 돋움; line-height: 18px; text-align: center; " />
</p></pre>
  
  <p style="color: rgb(51, 51, 51); font-family: 돋움; font-size: 12px; line-height: 18px; ">
    <b><br /></b>
  </p>
  
  <p style="color: rgb(51, 51, 51); font-family: 돋움; font-size: 12px; line-height: 18px; ">
    아래 첨부 파일은 매직 패킷을 Wireshark로 캡쳐한 것이다.[출처: Wireshark.org]
  </p>
  
  <p style="color: rgb(51, 51, 51); font-family: 돋움; font-size: 12px; line-height: 18px; ">
    Ether-wake와 UDP 패킷 2가지가 나와있다.
  </p>
  
  <p style="color: rgb(51, 51, 51); font-family: 돋움; font-size: 12px; line-height: 18px; text-align: center; ">
    <b></b>
  </p>
  
  <p style="color: rgb(51, 51, 51); font-family: 돋움; font-size: 12px; line-height: 18px; text-align: center; ">
    <a href="/images/1/cfile26.uf.125CBA4350259BC91C8AB5.pcap" class="aligncenter" filename="wol.pcap" filemime="application/vnd.tcpdump.pcap" />cfile26.uf.125CBA4350259BC91C8AB5.pcap</a>
  </p>
  
  <p style="color: rgb(51, 51, 51); font-family: 돋움; font-size: 12px; line-height: 18px; text-align: center; ">
    <b><br /></b>
  </p>
  
  <p style="color: rgb(51, 51, 51); font-family: 돋움; font-size: 12px; line-height: 18px; ">
    <b>매직 패킷을 보낼 수 있는 프로그램</b>
  </p>
  
  <p style="color: rgb(51, 51, 51); font-family: 돋움; font-size: 12px; line-height: 18px; ">
    <p>
      <b>Fusion WOL</b>
    </p>
    
    <p>
      <a href="http://fusionfenix.com/product/wol-1-0" target="_blank" class="tx-link">http://fusionfenix.com/product/wol-1-0</a>
    </p>
  </p>
  
  <p style="color: rgb(51, 51, 51); font-family: 돋움; font-size: 12px; line-height: 18px; ">
    찾아보면 이것말고 꽤 있다.
  </p>
  
  <p style="color: rgb(51, 51, 51); font-family: 돋움; font-size: 12px; line-height: 18px; ">
  </p>
  
  <p style="color: rgb(51, 51, 51); font-family: 돋움; font-size: 12px; line-height: 18px; text-align: center; clear: none; float: none; ">
    <img loading="lazy" src="/images/1/cfile10.uf.186855405022EBB3114680.png" class="aligncenter" width="395" height="360" filename="1.png" filemime="image/jpeg" />
  </p>
  
  <p style="color: rgb(51, 51, 51); font-family: 돋움; font-size: 12px; line-height: 18px; ">
  </p>
  
  <p style="color: rgb(51, 51, 51); font-family: 돋움; font-size: 12px; line-height: 18px; ">
  </p>
  
  <p style="color: rgb(51, 51, 51); font-family: 돋움; font-size: 12px; line-height: 18px; ">
    <b>W5200의 WOL 기능</b>
  </p>
  
  <p style="color: rgb(51, 51, 51); font-family: 돋움; font-size: 12px; line-height: 18px; ">
    -. Wake On LAN과 Power down mode와는 아무 관련이 없다. 그리고 power down mode를 enable하면 패킷을 못 받는다.
  </p>
  
  <p style="color: rgb(51, 51, 51); font-family: 돋움; font-size: 12px; line-height: 18px; ">
    -. 즉 WOL은 MCU가 sleep하고 있고, W5200은 동작하고 있는 상태에서 WOL기능을 이용해서 매직 패킷을 받으면 인터랍트가 떠서&nbsp;MCU 깨울때 사용하면 다.
  </p>
  
  <p style="color: rgb(51, 51, 51); font-family: 돋움; font-size: 12px; line-height: 18px; ">
    -. 단 주의 사항은 W5200은 ether-wake 패킷만 지원을 한다.&nbsp;
  </p>
  
  <p style="color: rgb(51, 51, 51); font-family: 돋움; font-size: 12px; line-height: 18px; ">
    &nbsp; &nbsp;따라서 PC에서 raw Ethernet Packet을 보낼 수 있는 프로그램이 필요하다.
  </p>
  
  <p style="color: rgb(51, 51, 51); font-family: 돋움; font-size: 12px; line-height: 18px; ">
  </p>
  
  <p style="color: rgb(51, 51, 51); font-family: 돋움; font-size: 12px; line-height: 18px; ">
    <b>참고</b>
  </p>
  
  <p>
    <a href="http://en.wikipedia.org/wiki/Wake-on-LAN" target="_blank" class="tx-link">http://en.wikipedia.org/wiki/Wake-on-LAN</a>
  </p>
  
  <p>
    <a href="http://wiki.wireshark.org/WakeOnLAN" target="_blank" class="tx-link">http://wiki.wireshark.org/WakeOnLAN</a>
  </p>
  
  <p>
    <a href="http://support.amd.com/us/Embedded_TechDocs/20213.pdf" target="_blank" class="tx-link">http://support.amd.com/us/Embedded_TechDocs/20213.pdf</a>
  </p>
</p>