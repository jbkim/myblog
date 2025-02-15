---
title: LeafLabs의 Maple mini, Maple Ret 5 보드 사용기
author: openmicrolab
type: post
date: 2011-11-25T11:31:38+00:00
url: /leaflabs의-maple-mini-maple-ret-5-보드-사용기/
dsq_thread_id:
  - "1224943401"
categories:
  - Open Source Hardware
tags:
  - Arduino
  - 오픈소스 하드웨어
  - open hardware
  - Leaflabs
  - maple

---
<A title="[http://arduino.cc]로 이동합니다." href="http://arduino.cc/" target=_blank>Arduino</A>가 AVR을 기반으로 하여 오픈하드웨어 플랫폼을 주도하고 있는데, <A title="[http://leaflabs.com/]로 이동합니다." href="http://leaflabs.com/" target=_blank>Leaflabs</A>은&nbsp;STM32시리즈를 기반으로 하는 오픈하드웨어 플랫폼을 만들고 있다.&nbsp;<A title="[http://leaflabs.com/]로 이동합니다." href="http://leaflabs.com/" target=_blank>Leaflabs</A>의 보드들의 이름은 Maple이다.  
<A title="[http://leaflabs.com/]로 이동합니다." href="http://leaflabs.com/" target=_blank>Leaflabs</A>사의 홈페이지에서 주문을 하니 한 일주일만에 배송이 되었다. <A title="[http://arduino.cc]로 이동합니다." href="http://arduino.cc/" target=_blank>Arduino</A>가 요즘에는 브랜딩 작업을 하고 있고, 포장 및 디자인까지 신경을 쓰는 반면 역시 후발 주자답게 포장이 좀 허접하다. 대신 사탕을 같이 넣어서 주네..ㅋㅋ

<P style="MARGIN: 0px">
  <img loading="lazy" src="/images/1/cfile23.uf.180B40494ECF78311B6A81.jpg" class="aligncenter" width="490" height="322" alt="" filename="Maple with Candy.jpg" filemime="image/jpeg" />
</P>

  


<P style="MARGIN: 0px">
  <img loading="lazy" src="/images/1/cfile6.uf.180B55484ECF78B6227356.jpg" class="aligncenter" width="551" height="331" alt="" filename="Maple.jpg" filemime="image/jpeg" />
</P>

  
아두이노와 같은 모습의 IDE를 사용하는데, 일단 처음 부터 막힌다. <A title="[http://static.leaflabs.com/pub/leaflabs/maple-ide/maple-ide-0.0.12-windowsxp32.zip]로 이동합니다." href="http://static.leaflabs.com/pub/leaflabs/maple-ide/maple-ide-0.0.12-windowsxp32.zip" target=_blank>IDE 다운로드</A>

<P style="MARGIN: 0px">
  <img loading="lazy" src="/images/1/cfile23.uf.127C0E4C4ECF7A212BB755.png" class="aligncenter" width="436" height="522" alt="" filename="Maple_IDE.png" filemime="image/jpeg" />
</P>

  
몇시간의 삽질끝과 <A title="[http://leaflabs.com/docs/bootloader.html]로 이동합니다." href="http://leaflabs.com/docs/bootloader.html" target=_blank>bootloader</A> 소스까지 받아서 bootloader 가 어떻게 동작을 하는지 알아낸 후에야 이해가 된다.  
Windows 환경의 경우 드라이버를 수동으로 설치를 해야 하는데 2 종류의 드라이버를 설치를 해야한다.  
&nbsp;-. Maple R3 COM port 드라이버  
&nbsp;-. LibUSB-Win32 Devices 드라이버  
만약&nbsp;위 2번째 드라이버가 설치가 안되어 있으면, 다운로드시

<P style="MARGIN: 0cm 0cm 0pt; mso-margin-top-alt: auto; mso-margin-bottom-alt: auto" class=MsoNormal><SPAN><FONT color=#000000 size=3><SPAN style="FONT-SIZE: 10pt"><STRONG>Couldn&#8217;t find the DFU device: [1EAF:0003]</STRONG></SPAN></FONT><?xml:namespace prefix = u1 /><u1:p></u1:p>

<?xml:namespace prefix = o ns = "urn:schemas-microsoft-com:office:office" /><o:p></o:p></SPAN>

  


라는 메시지가 뜬다.

설치를 하는 방법이 좀 까다로운데, 리셋을 누르면 LED가 6번 빨리 깜박인다.  
이 다음에 BUT 버튼을 누른후 장지관리자에서 설치가 되지 않은 드라이버를 수동으로 설치를 한다.  
즉 Perpetual bootloader mode에서 설치를 해야 한다.  
설치 파일은 IDE를 인스톨한 폴더 아래 drivers\mapleDrv 아래 dfu, serial 폴더에 각각 있다.

LeafLabs에 있는 Andrew가 알려준 유튜브에 있는 동영상  


  


<P style="TEXT-ALIGN: center">
</p>



  


<P style="TEXT-ALIGN: left">
  <A href="http://leaflabs.com/docs/maple-ide-install.html#id4">http://leaflabs.com/docs/maple-ide-install.html#id4</A>&nbsp;에 있는 설치 정보.
</p>



  


<P style="TEXT-ALIGN: justify; WIDOWS: 2; TEXT-TRANSFORM: none; BACKGROUND-COLOR: rgb(255,255,255); TEXT-INDENT: 0px; LETTER-SPACING: normal; FONT: 16px/20px Lucidia; WHITE-SPACE: normal; ORPHANS: 2; COLOR: rgb(0,0,0); WORD-SPACING: 0px; -webkit-text-size-adjust: auto; -webkit-text-stroke-width: 0px">
  <SPAN style="FONT-SIZE: 11pt">First, install DFU drivers (for uploading code to your Maple) using the following steps.</SPAN>
</P>

  


<OL style="WIDOWS: 2; TEXT-TRANSFORM: none; BACKGROUND-COLOR: rgb(255,255,255); LIST-STYLE-TYPE: decimal; TEXT-INDENT: 0px; LETTER-SPACING: normal; FONT: 16px Lucidia; WHITE-SPACE: normal; ORPHANS: 2; COLOR: rgb(0,0,0); WORD-SPACING: 0px; -webkit-text-size-adjust: auto; -webkit-text-stroke-width: 0px" class="arabic simple">
  <br /> 
  
  <LI style="TEXT-ALIGN: justify; LINE-HEIGHT: 20px">
    <SPAN style="FONT-SIZE: 11pt">Plug your Maple into the USB port.</SPAN>
  </LI>
  <br /> 
  
  <LI style="TEXT-ALIGN: justify; LINE-HEIGHT: 20px">
    <SPAN style="FONT-SIZE: 11pt">Hit the reset button on your Maple (it’s the small button at the bottom left, labeled RESET). Notice that it blinks quickly 6 times, then blinks slowly a few more times.</SPAN>
  </LI>
  <br /> 
  
  <LI style="TEXT-ALIGN: justify; LINE-HEIGHT: 20px">
    <SPAN style="FONT-SIZE: 11pt">Hit reset again, and this time push and hold the other button during the 6 fast blinks (the button is on the top right; it is labeled BUT). You can release it once the slow blinks start.</SPAN>
  </LI>
  <br /> 
  
  <LI style="TEXT-ALIGN: justify; LINE-HEIGHT: 20px">
    <SPAN style="FONT-SIZE: 11pt">Your Maple is now in</SPAN><SPAN class=Apple-converted-space><SPAN style="FONT-SIZE: 11pt">&nbsp;</SPAN></SPAN><A style="COLOR: green; TEXT-DECORATION: none" class="reference internal" href="http://leaflabs.com/docs/troubleshooting.html#troubleshooting-perpetual-bootloader"><EM><SPAN style="FONT-SIZE: 11pt">perpetual bootloader mode</SPAN></EM></A><SPAN style="FONT-SIZE: 11pt">. This should give you a chance to install the DFU drivers.</SPAN>
  </LI>
  <br /> 
  
  <LI style="TEXT-ALIGN: justify; LINE-HEIGHT: 20px">
    <SPAN style="FONT-SIZE: 11pt">Windows should now prompt you for some drivers. In the top level directory of the Maple IDE, point Windows to</SPAN><SPAN class=Apple-converted-space><SPAN style="FONT-SIZE: 11pt">&nbsp;</SPAN></SPAN><TT style="PADDING-BOTTOM: 0px; BACKGROUND-COLOR: rgb(236,240,243); PADDING-LEFT: 1px; PADDING-RIGHT: 1px; FONT-SIZE: 0.95em; PADDING-TOP: 0px" class="file docutils literal"><SPAN class=pre><SPAN style="FONT-SIZE: 11pt">drivers/mapleDrv/dfu/</SPAN></SPAN></TT><SPAN style="FONT-SIZE: 11pt">.</SPAN>
  </LI>
</OL>

  


<P style="TEXT-ALIGN: justify; WIDOWS: 2; TEXT-TRANSFORM: none; BACKGROUND-COLOR: rgb(255,255,255); TEXT-INDENT: 0px; LETTER-SPACING: normal; FONT: 16px/20px Lucidia; WHITE-SPACE: normal; ORPHANS: 2; COLOR: rgb(0,0,0); WORD-SPACING: 0px; -webkit-text-size-adjust: auto; -webkit-text-stroke-width: 0px">
  <SPAN style="FONT-SIZE: 11pt">Next, install serial drivers (for communicating with your Maple using serial over USB).</SPAN>
</P>

  


<OL style="WIDOWS: 2; TEXT-TRANSFORM: none; BACKGROUND-COLOR: rgb(255,255,255); LIST-STYLE-TYPE: decimal; TEXT-INDENT: 0px; LETTER-SPACING: normal; FONT: 16px Lucidia; WHITE-SPACE: normal; ORPHANS: 2; COLOR: rgb(0,0,0); WORD-SPACING: 0px; -webkit-text-size-adjust: auto; -webkit-text-stroke-width: 0px" class="arabic simple">
  <br /> 
  
  <LI style="TEXT-ALIGN: justify; LINE-HEIGHT: 20px">
    <SPAN style="FONT-SIZE: 11pt">Reset your Maple and allow it to exit the bootloader (wait for the slow blinking to stop). The Maple will next start running whatever program was uploaded to it last. (New Maples will start running the test program we upload to them before shipping them to you).</SPAN>
  </LI>
  <br /> 
  
  <LI style="TEXT-ALIGN: justify; LINE-HEIGHT: 20px">
    <SPAN style="FONT-SIZE: 11pt">Once Maple is running some user code, Windows should prompt you for more drivers. Point windows to</SPAN><SPAN class=Apple-converted-space><SPAN style="FONT-SIZE: 11pt">&nbsp;</SPAN></SPAN><TT style="PADDING-BOTTOM: 0px; BACKGROUND-COLOR: rgb(236,240,243); PADDING-LEFT: 1px; PADDING-RIGHT: 1px; FONT-SIZE: 0.95em; PADDING-TOP: 0px" class="file docutils literal"><SPAN class=pre><SPAN style="FONT-SIZE: 11pt">driver/mapleDrv/serial</SPAN></SPAN></TT><SPAN style="FONT-SIZE: 11pt">.</SPAN>
  </LI>
</OL>

  


<P style="TEXT-ALIGN: left">
</p>

일단 각각의 드라이버가 설치가 잘 되면 그 다음은 Arduino에서 작업을 하듯 할 수 있다.



  


<DIV style="MARGIN-LEFT: 4em">
  &nbsp;</p> 
  
  <p>
    </DIV>
  </p>