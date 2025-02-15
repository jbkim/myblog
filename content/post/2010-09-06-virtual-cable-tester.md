---
title: Virtual Cable Tester
author: openmicrolab
type: post
date: 2010-09-06T08:32:40+00:00
url: /virtual-cable-tester/
dsq_thread_id:
  - "1126110544"
categories:
  - Infomation
  - Development
tags:
  - Ethernet
  - Ethernet PHY
  - Marvell
  - PHY
  - VCT
  - 이더넷

---
<span style="font-size: 11pt; ">Ethernet 네트워크에서는 필수적으로 Ethernet PHY 칩을 사용해야한다. PHY칩에 적용되는 기술중 하나인 <b>VCT(Virtual Cable Tester)</b>는 Marvell에서 개발한 기술로 간단히 얘기하면 <a href="http://liketheocean.tistory.com/entry/%EC%9D%B4%EB%8D%94%EB%84%B7-%EC%BC%80%EC%9D%B4%EB%B8%94-%EC%A2%85%EB%A5%98-UTP-FTP-STP" target="_blank" title="[http://liketheocean.tistory.com/entry/%EC%9D%B4%EB%8D%94%EB%84%B7-%EC%BC%80%EC%9D%B4%EB%B8%94-%EC%A2%85%EB%A5%98-UTP-FTP-STP]로 이동합니다.">UTP 케이블</a>의 단선 및 단락등을 검출하는 기술이다.&nbsp;</span>

<div>
  <span style="font-size: 11pt; ">즉 구체적으로 다음과 같은 문제점의 검출이 가능하다.</span>
</div>

<div>
</div>

<div>
  <span class="Apple-style-span" style="color: rgb(0, 0, 0); font-family: arial, helvetica; line-height: normal; font-size: 17px; -webkit-border-horizontal-spacing: 2px; -webkit-border-vertical-spacing: 2px; "></p> 
  
  <ul class="point_normal" style="font-family: arial, helvetica; font-size: 9pt; ">
    <li class="point_normal" style="font-family: arial, helvetica; font-size: 9pt; ">
      <span class="title_emph" style="font-family: arial, helvetica; font-size: 9pt; font-weight: bold; "><span style="font-size: 11pt; ">Open:</span></span><span style="font-size: 11pt; ">&nbsp; Lack of continuity between the pins at each end of the twisted-pair cable.</span>
    </li>
    <li class="point_normal" style="font-family: arial, helvetica; font-size: 9pt; ">
      <span class="title_emph" style="font-family: arial, helvetica; font-size: 9pt; font-weight: bold; "><span style="font-size: 11pt; ">Short:</span></span><span style="font-size: 11pt; ">&nbsp; Two or more conductors short-circuited together.</span>
    </li>
    <li class="point_normal" style="font-family: arial, helvetica; font-size: 9pt; ">
      <span class="title_emph" style="font-family: arial, helvetica; font-size: 9pt; font-weight: bold; "><span style="font-size: 11pt; ">Crossed pair:</span></span><span style="font-size: 11pt; ">&nbsp; Twisted-pair cable incorrectly connected at one end. For example, pair 3 is connected to pins 4 and 5 on one end, and pins 7 and 8 on the other end.</span>
    </li>
    <li class="point_normal" style="font-family: arial, helvetica; font-size: 9pt; ">
      <span class="title_emph" style="font-family: arial, helvetica; font-size: 9pt; font-weight: bold; "><span style="font-size: 11pt; ">Reversed pair:</span></span><span style="font-size: 11pt; ">&nbsp; Two conductors in a twisted-pair cable connected with reverse polarity. For example, one conductor in pair 3 is connected to pin 1 on one side and to pin 2 on the other, while the second conductor is connected between pin 2 and pin 1.</span>
    </li>
    <li class="point_normal" style="font-family: arial, helvetica; font-size: 9pt; ">
      <span class="title_emph" style="font-family: arial, helvetica; font-size: 9pt; font-weight: bold; "><span style="font-size: 11pt; ">Improper termination:</span></span><span style="font-size: 11pt; ">&nbsp; Cable terminations not equal to 100 ohms. Because the characteristic impedance of Category 5 (Cat 5) cable is 100 ohms, the cable terminations at each end must also be 100 ohms to prevent waveform reflections and potential data errors.</span>
    </li>
  </ul>
  
  <p>
    </span></div> 
    
    <div>
      </p> 
      
      <div>
        <span class="Apple-style-span" style="line-height: 22px; font-size: 15px; ">예를 들면 UTP케이블이 100m 짜리인데 중간에 어느 부근에서 단선, 단락이 되었는지, 선이 제대로 연결이 되었는지 등을 알 수있다.</span>
      </div>
      
      <div>
        <span class="Apple-style-span" style="line-height: 22px; font-size: 15px; ">이 기술로 원리는 특정 파형의 시그널을 보내고 이것이 반사되어 오는 시간 및 패턴을 보고 문제의 원인을 알아낸다.</span>
      </div>
      
      <div>
        <span style="font-size: 11pt; "><br /> </span>
      </div>
      
      <div>
        <span style="font-size: 11pt; "><img loading="lazy" src="/images/1/cfile9.uf.172DD9334C84A635787D06.jpg" class="aligncenter" width="432" height="341" alt="" filename="marvell_vct.jpg" filemime="image/jpeg" /><br /> </span>
      </div>
      
      <div>
        <span style="font-size: 11pt; "><img loading="lazy" src="/images/1/cfile23.uf.14074A1E4C84A677854F2F.jpg" class="aligncenter" width="432" height="341" alt="" filename="marvell_vct2.jpg" filemime="image/jpeg" /><br /> </span>
      </div>
      
      <div>
        <span style="font-size: 11pt; "><a href="http://www.marvell.com" target="_blank" title="[http://www.marvell.com]로 이동합니다.">Marvell의 홈페이지</a>에서는 관련한 내용이 잘 찾아지지 않는데, 아래 링크의 내용은 Dell의 제품에 적용된 내용을 기술한 내용이다. &nbsp;</span><a href="http://www.dell.com/content/topics/global.aspx/power/en/ps2q03_marvell?c=us&l=en&cs=555" target="_blank" title="[http://www.dell.com/content/topics/global.aspx/power/en/ps2q03_marvell?c=us&l=en&cs=555]로 이동합니다."><span style="font-size: 11pt; ">관련 내용 참고</span></a><span style="font-size: 11pt; ">&nbsp;</span>
      </div>
    </div>
    
    <div>
      <span style="font-size: 11pt; "><br /> </span>
    </div>