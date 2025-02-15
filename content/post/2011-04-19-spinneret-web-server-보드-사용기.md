---
title: Spinneret Web Server 보드 사용기
author: openmicrolab
type: post
date: 2011-04-19T11:25:11+00:00
url: /spinneret-web-server-보드-사용기/
dsq_thread_id:
  - "1171513006"
categories:
  - Open Source Hardware
tags:
  - WIZNET
  - parallax
  - Propeller
  - spinneret web server

---
Spinneret의 뜻은 (동물) (거미·누에 등의) 방적 돌기 ((실이 나오는 구멍))&#8230; 보드에 뒷면에 거미와 거미줄 그림이 있다&#8230;.

<P style="MARGIN: 0px">
  <img loading="lazy" src="/images/1/cfile21.uf.155924474DAD7100060ABA.jpg" class="aligncenter" width="426" height="158" alt="" filename="2011-04-19 20.22.00.jpg" filemime="image/jpeg" />
</P>

  
이 보드는 Parallax([www.parallax.com][1])사의 Propeller칩과 Wiznet([www.wiznet.co.kr][2])의 W5100이 내장된 웹서버 보드이다.  
웹서버 어플리케이션을 위해 mSD카드도 장착이 되어 있다.  
Open Source Hardware 플랫폼을 지향하기 때문에 모든 자료들은 웹상에 오픈이 되어 있다.  
하지만 Propellar칩은 코아가 8개가 들어간 병렬칩으로 좀 생소하기 때문에 익숙해 지기까지는 좀 시간이 걸릴 것 같다.  
각 코아는 Cog라고 불린다. 아래 그림 참고..

<P style="MARGIN: 0px">
  <img loading="lazy" src="/images/1/cfile9.uf.1502D04D4DAD6B10130C5D.jpg" class="aligncenter" width="683" height="439" alt="" filename="PropellerBlock-L.jpg" filemime="image/jpeg" />
</P>

  
일단 필요한 것은 개발툴 및 메뉴얼을 <http://www.parallax.com/tabid/832/Default.aspx>&nbsp;에서 다운받아서 설치를 하는데, 컴파일러&nbsp; <SPAN style="WIDOWS: 2; TEXT-TRANSFORM: none; TEXT-INDENT: 0px; BORDER-COLLAPSE: separate; FONT: medium Gulim; WHITE-SPACE: normal; ORPHANS: 2; LETTER-SPACING: normal; COLOR: rgb(0,0,0); WORD-SPACING: 0px; -webkit-border-horizontal-spacing: 0px; -webkit-border-vertical-spacing: 0px; -webkit-text-decorations-in-effect: none; -webkit-text-size-adjust: auto; -webkit-text-stroke-width: 0px" class=Apple-style-span><SPAN style="BORDER-COLLAPSE: collapse; FONT-FAMILY: Verdana, Geneva, Arial, Helvetica, sans-serif; COLOR: rgb(32,32,82); FONT-SIZE: 10px; -webkit-border-horizontal-spacing: 2px; -webkit-border-vertical-spacing: 2px" class=Apple-style-span>**Propeller/Spin Tool Software v1.2.7 (R2)** </SPAN></SPAN>를 다운 받아서 설치를 하면 serial terminal 및 메뉴얼까지&nbsp;설치가 된다.

<P style="MARGIN: 0px">
  <img loading="lazy" src="/images/1/cfile25.uf.1748C24A4DAD6C782E9A55.jpg" class="aligncenter" width="250" height="250" alt="" filename="32203-M.jpg" filemime="image/jpeg" />
</P>

  
Spinneret Web Server 보드 관련 자료는  
<http://www.parallax.com/Store/Microcontrollers/PropellerDevelopmentBoards/tabid/514/ProductID/710/List/0/Default.aspx?SortField=ProductName,ProductName>&nbsp; 에서 다운로드하면 된다. 

<DIV style="TEXT-ALIGN: left">
  <STRONG>Spinneret Web Server Docs (.pdf) </STRONG>
</DIV>

  


<P style="MARGIN: 0px">
  <a href="/images/1/cfile8.uf.134EAE4F4DAD6D0026BE33.pdf" class="aligncenter" filename="32203-SpinneretWebServerDoc-v1.1.pdf"  filemime="application/pdf" />cfile8.uf.134EAE4F4DAD6D0026BE33.pdf</a>
</P>

  
**Spinneret Schematic (.pdf)**  


<P style="MARGIN: 0px">
  <a href="/images/1/cfile8.uf.1647D44F4DAD6D183786D9.pdf" class="aligncenter" filename="SpinneretWebServerSchematicRevA.pdf"  filemime="application/pdf" />cfile8.uf.1647D44F4DAD6D183786D9.pdf</a>
</P>

  
**WIZnet W5100 SPI Driver (OBEX)** <http://obex.parallax.com/objects/614/>&nbsp;에서 다운로드

<P style="MARGIN: 0px">
  <img loading="lazy" src="/images/1/cfile23.uf.111BCE494DAD6F851AA5EB.jpg" class="aligncenter" width="179" height="156" alt="" filename="32201-M.jpg" filemime="image/jpeg" />
</P>

  


<DIV style="TEXT-ALIGN: center">
  <STRONG>Prop Plug : FTDI의 USB to Serial 칩이 내장된 모듈 보드<br /> </STRONG><br />
</DIV>

  


<DIV>
  전원을 J6의 2,3번에 5V를 입력하면 보드가 동작을 하고, 설치된 컴파일러에서 바이너리를 J2에 연결된 Prop plug를 통해 다운로드하면 된다.
</DIV>

  


<P style="MARGIN: 0px">
  <img loading="lazy" src="/images/1/cfile8.uf.164A3F474DAD6E7A1AEC7C.jpg" class="aligncenter" width="653" height="465" alt="" filename="propeller.jpg" filemime="image/jpeg" />
</P>

  
동작하는 시리얼 터미널 프로그램.

<P style="MARGIN: 0px">
  <img loading="lazy" src="/images/1/cfile4.uf.153CF7474DAD6EB7387AB8.jpg" class="aligncenter" width="541" height="202" alt="" filename="propeller_serial.jpg" filemime="image/jpeg" />
</P>

 [1]: http://www.parallax.com/
 [2]: http://www.wiznet.co.kr/