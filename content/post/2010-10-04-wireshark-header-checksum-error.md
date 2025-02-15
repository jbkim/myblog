---
title: Wireshark Header Checksum Error
author: openmicrolab
type: post
date: 2010-10-04T04:07:46+00:00
url: /wireshark-header-checksum-error/
dsq_thread_id:
  - "1174385535"
categories:
  - Development
  - Network
tags:
  - wireshark
  - 와이어샤크
  - 체크섬에러
  - 패킷 분석

---
<span style="font-size: 11pt; "><span style="font-size: 11pt; ">﻿</span>와이어샤크를 사용해서 패킷을 잡다보면 패킷에 &#8220;<b>Header Checksum Error</b>&#8220;라고 표시가 되어 있는 것을 볼 수 있다. 그리고 친절하게도 어떤값이 되어야 한다고 알려주기까지 한다.</span>

<div>
  <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px;"><br /> </span></font></p> 
  
  <div>
    <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px;"><img loading="lazy" src="/images/1/cfile29.uf.2072920F4CA951186C030E.jpg" class="aligncenter" width="460" height="83" alt="" filename="ChecksumError.jpg" filemime="image/jpeg" /><br /> </span></font>
  </div>
  
  <div>
    <div>
      <span style="font-size: 11pt; ">체크섬이라는 것은 일반적으로 통신중에 데이터가 깨질수 도있기 때문에&nbsp;</span><span class="Apple-style-span" style="line-height: 22px; font-size: 15px; ">삽입을 해서 데이터가 깨졌는지 여부를 확인을 한다.&nbsp;</span>
    </div>
    
    <div>
      <span class="Apple-style-span" style="line-height: 22px; font-size: 15px; "></span><span style="font-size: 10pt; "><span style="font-size: 11pt; ">IP 헤더의 경우를 보면 2 바이트로&nbsp;</span></span><span class="Apple-style-span" style="line-height: 22px; font-size: 15px; ">구성되어 있고, 네트워크를 이동하는 각 홉에서(예를 들면, 라우터 통과시) 체크섬을 검증한다.&nbsp;</span><span class="Apple-style-span" style="line-height: 22px; font-size: 15px; ">그리고&nbsp;</span><span class="Apple-style-span" style="line-height: 22px; font-size: 15px; ">체크섬이 올바르지 않으면 네트워크 장비는 해당 패킷을 버리며,&nbsp;</span><span class="Apple-style-span" style="line-height: 22px; font-size: 15px; ">체크섬은 재 계산되고 업데이트를 하게된다.</span>
    </div>
  </div>
  
  <div>
    <span class="Apple-style-span" style="line-height: 22px; font-size: 15px; "><br /> </span>
  </div>
  
  <div>
    <span class="Apple-style-span" style="line-height: 22px; font-size: 15px; ">그럼 어떻게 헤더체크섬이 틀린 패킷을 보내고 받을 수 있지??</span>
  </div>
  
  <div>
    <span class="Apple-style-span" style="line-height: 22px; font-size: 15px; ">원인은 여러가지가 있을 수 있는데 <b>UDP의 경우는&nbsp;</b></span><span class="Apple-style-span" style="line-height: 22px; font-size: 15px; "><b>체크섬 값이 제로로 채워져 있는 경우는 보내는 측 쪽에서 계산되지 않는 경우라 정의하고 있다. (</b></span><span class="Apple-style-span" style="line-height: 22px; font-size: 15px; "><b>RFC 768)</b></span><span class="Apple-style-span" style="line-height: 22px; font-size: 15px; ">&nbsp;&nbsp;</span><span class="Apple-style-span" style="line-height: 22px; font-size: 15px; "><b>그리고&nbsp;</b></span><span class="Apple-style-span" style="line-height: 22px; font-size: 15px; "><b>네트워크 장비나 기타 원인에 의해 헤더 체크섬 값이 계산되지 않았거나&nbsp;</b></span><span class="Apple-style-span" style="line-height: 22px; font-size: 15px; "><b>또는 의도적으로 빠지는 경우도 있다.</b></span>
  </div>
  
  <div>
    <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px;"></p> 
    
    <div>
    </div>
    
    <div>
      와이어샤크에서 패킷 분석시 이게 거슬리면 다음과 같이 와이어샤크의 옵션에서 설정을 바꾸면 된다.
    </div>
    
    <div>
      <b>Edit > Preferences.. > 좌측 맨 하단의 Protocols를 선택후 UDP를 선택 > Validate the UDP checksum if possible 옵션을 해제한다.</b>
    </div>
    
    <div>
      <b><br /> </b>
    </div>
    
    <div>
      <img loading="lazy" src="/images/1/cfile4.uf.1734CC114CA952733F3BEC.jpg" class="aligncenter" width="680" height="357" alt="" filename="Wireshark_UDP.jpg" filemime="image/jpeg" />
    </div>
    
    <div>
      TCP의 경우도 마찬가지&#8230;
    </div>
    
    <div>
    </div>
    
    <p>
      </span></font></div> </div>