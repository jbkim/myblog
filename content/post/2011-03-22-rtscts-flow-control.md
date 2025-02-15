---
title: RTS/CTS flow control
author: openmicrolab
type: post
date: 2011-03-22T06:17:04+00:00
url: /rtscts-flow-control/
dsq_thread_id:
  - "1181701842"
categories:
  - Infomation
  - Development
tags:
  - 시리얼통신
  - Flow control
  - RTS/CTS flow control

---
시리얼 통신에서 H/W flow control은 RTS, CTS signal을 사용을 한다.  
아래 자료는 ST의 칩 데이터시트에서 가져온 내용인데, RTS/CTS flow control에 대해 쉽게 이해가 된다.  
**  
<U><FONT color=#e31600>RTS 신호가 RX 회로쪽에 CTS 신호가 TX 회로쪽에 연결이 되어 있다는 점에 유의하자.<br /> </FONT></U>**

<P style="MARGIN: 0px">
  <img loading="lazy" src="/images/1/cfile23.uf.20023B334D883E8D2B0FA8.jpg" class="aligncenter" width="561" height="645" alt="" filename="HW_FlowControl_1.jpg" filemime="image/jpeg" />
</P>

  


<P style="MARGIN: 0px">
  <img loading="lazy" src="/images/1/cfile2.uf.1835C3364D883EAB381C2F.jpg" class="aligncenter" width="550" height="129" alt="" filename="HW_FlowControl_2.jpg" filemime="image/jpeg" />
</P>

  


<P style="MARGIN: 0px">
  <img loading="lazy" src="/images/1/cfile2.uf.116F3C354D883EB4352522.jpg" class="aligncenter" width="552" height="324" alt="" filename="HW_FlowControl_3.jpg" filemime="image/jpeg" />
</P>

**1. RTS flow control  
** RTS 신호는 수신이 가능한 상태이면 Low로 되며, 수신이 불가능하면 High로 한다.

**2. CTS flow control  
** TX를 하기전에 CTS 입력을 확인해서 CTS가 Low이면 데이터를 보낸다.

**즉 Hardware Flow control을 사용한다면, 데이터를 보내기전에 CTS 입력(상대방의 RTS)을 확인하여 이것이 Low이면 데이터를 보내고, 데이터를 수신시에는 버퍼가 어느 정도까지 차면(buffer full)&nbsp;RTS를 High로 하고, 나머지 상태에서는 Low로&nbsp; 하면 된다.</p> 

</STRONG>