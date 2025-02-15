---
title: Wi-Fi Provisioning
author: openmicrolab
type: post
date: 2011-01-28T05:01:12+00:00
url: /wi-fi-provisioning/
dsq_thread_id:
  - "1373818979"
categories:
  - Development
  - Network

---
<FONT color=#000000>Provisioning의 의미는 위키피디어에 정의되어 있는 내용을 살펴보면 다음과 같다.

In telecommunication, provisioning is the process of preparing and equipping a network to allow it to provide (new) services to its users. In NS/EP telecommunications services, &#8220;provisioning&#8221; equates to &#8220;initiation&#8221; and includes altering the state of an existing priority service or capability.

핵심적인 얘기는 the process of preparing and equipping a network&#8230;

즉 통신(네트워크)에서 사용자에게 네트워킹을 가능하게 해주는 절차 및 방법 이라고 이해하면 될 듯&#8230;

이것이 일반적인 유선이라면 별 무리가 없지만 무선의 경우는 얘기가 좀 달라진다.  
왜냐면 일단 무선의 경우 선이 없으니 문제가 생기면 더 복잡하며, 사용자에게&nbsp;가장 편리한 방법을 제공하는 것이 키포인트이다.  
특히 사용자 시스템이 유저인터페이스가 없는 경우 즉 LCD나 키패드 같은 것이 없는 임베디스 시스템의 경우 더욱더 중요하다.

참고로 아래 내용은 임베디드 WiFi 솔루션을 제공하는 Gainspan의 자료임.

</FONT>  


<DIV style="TEXT-ALIGN: center">
  </p> 
  
  <p>
    </DIV><br /> 
    
    <DIV style="TEXT-ALIGN: left">
      <FONT color=#000000>Wi-Fi client가 네트워크에 연결이 되려면 무조건 AP에 접속이 되야 하는데, 여러가지 방법이 있다.<br /> GainSpan에서는 다음과 같이 3가지 방법을 소개하고 있다.</p> 
      
      <p>
        <STRONG>1. WPS(Wi-Fi Protected Setup)</STRONG><br /> &nbsp; AP가 WPS를 지원을 할 경우 가능한 방법이며, WPS를 이용해 AP에 무선으로 연결이 되고, DHCP를 통해 IP를 받는다.<br /> <img loading="lazy" src="/images/1/cfile21.uf.191887544D424CD907A902.jpg" class="aligncenter" width="480" height="155.8238172920065" alt="" filename="cfile21.uf.191887544D424CD907A902.jpg" filemime="" /></FONT><br /> <FONT color=#000000><STRONG>2. Ad hoc browser<br /> </STRONG>&nbsp;&nbsp; 우선 Ad hoc을 통해 노트북과 연결이 되고, Wi-Fi client에서 동작하고 있는 웹서버에 접속해서 네트워크 설정을 한다.<br /> &nbsp;&nbsp; 이 설정대로 AP에 접속이 된다.<br /> <img loading="lazy" src="/images/1/cfile9.uf.1756A3554D424CEC045DEE.jpg" class="aligncenter" width="320" height="306" alt="" filename="cfile9.uf.1756A3554D424CEC045DEE.jpg" filemime="" />
      </p>
      
      <p>
        <STRONG>3. Ad hoc custom APP</STRONG><br /> &nbsp;&nbsp; Ad hoc browser와 내용이 동일한데, 노트북을 이용해 접속하는 것이 아니고 스마트폰에서&nbsp;앱을 작성해서 Wi-Fi client에 접속을 하는 것만 다르다.<br /> </FONT></DIV><br /> 
        
        <DIV>
          <img loading="lazy" src="/images/1/cfile6.uf.1924BF524D424D020FB869.jpg" class="aligncenter" width="320" height="313" alt="" filename="cfile6.uf.1924BF524D424D020FB869.jpg" filemime="" /></p> 
          
          <p>
            </DIV>
          </p>