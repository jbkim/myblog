---
title: '[IO 포트] push-pull, open drain'
author: openmicrolab
type: post
date: 2011-01-31T01:44:52+00:00
url: /io-포트-push-pull-open-drain/
dsq_thread_id:
  - "1183515624"
categories:
  - Development
  - Semiconductor
tags:
  - open drain
  - push-pull

---
<SPAN style="WIDOWS: 2; TEXT-TRANSFORM: none; TEXT-INDENT: 0px; BORDER-COLLAPSE: separate; FONT: medium Gulim; WHITE-SPACE: normal; ORPHANS: 2; LETTER-SPACING: normal; COLOR: rgb(0,0,0); WORD-SPACING: 0px; -webkit-border-horizontal-spacing: 0px; -webkit-border-vertical-spacing: 0px; -webkit-text-decorations-in-effect: none; -webkit-text-size-adjust: auto; -webkit-text-stroke-width: 0px" class=Apple-style-span><SPAN style="TEXT-ALIGN: justify; LINE-HEIGHT: 21px; FONT-FAMILY: Tahoma; COLOR: rgb(85,85,85); FONT-SIZE: 12px" class=Apple-style-span><SPAN style="FONT-SIZE: 10pt">아래 자료는 </SPAN><SPAN style="WIDOWS: 2; TEXT-TRANSFORM: none; TEXT-INDENT: 0px; BORDER-COLLAPSE: separate; FONT: medium Gulim; WHITE-SPACE: normal; ORPHANS: 2; LETTER-SPACING: normal; COLOR: rgb(0,0,0); WORD-SPACING: 0px; -webkit-border-horizontal-spacing: 0px; -webkit-border-vertical-spacing: 0px; -webkit-text-decorations-in-effect: none; -webkit-text-size-adjust: auto; -webkit-text-stroke-width: 0px" class=Apple-style-span><SPAN style="TEXT-ALIGN: left; LINE-HEIGHT: 18px; FONT-FAMILY: Tahoma; COLOR: rgb(85,85,85); FONT-SIZE: 12px" class=Apple-style-span><A style="FONT: bold 20px Tahoma, 굴림, sans-serif; COLOR: rgb(0,0,0); TEXT-DECORATION: none" href="http://irmus.tistory.com/"><A title="[http://irmus.tistory.com/]로 이동합니다." href="http://irmus.tistory.com/" target=_blank><SPAN style="FONT-SIZE: 10pt">irmus</SPAN></A></A><SPAN style="FONT-SIZE: 10pt">&nbsp;님의 자료입니다. ^^;</SPAN>  
</SPAN></SPAN>  
MCU나 74 시리즈 로직 칩들을 보다 보면 출력 타입이 여러가지가 있는 것을 볼 수 있다. 가장 기본적이면서 또 그만큼 많이 사용되는 두가지 출력 타입에 대해 이야기 해보려 한다. push-pull 타입과 open drain(혹은 open collector) 타입이 그것이다.

<DIV style="BORDER-BOTTOM: rgb(180,153,126) 1px solid; BORDER-LEFT: rgb(180,153,126) 1px solid; PADDING-BOTTOM: 10px; BACKGROUND-COLOR: rgb(230,216,201); PADDING-LEFT: 10px; PADDING-RIGHT: 10px; BORDER-TOP: rgb(180,153,126) 1px solid; BORDER-RIGHT: rgb(180,153,126) 1px solid; PADDING-TOP: 10px">
  Drain은 MOSFET의 Drain 핀을 의미한다. Collector는 BJT의 Collector이다. Open drain과 open collector는 동일한 동작 원리를 가지는 구성을 MOSFET로 만들었느냐 BJT로 만들었느냐의 차이일 뿐이다. 반면 push-pull 출력은 BJT나 MOSFET나 모두 같은 이름을 사용한다.
</DIV>

<DIV style="TEXT-ALIGN: center" class="imageblock dual">
  <br /> <TABLE style="BACKGROUND-IMAGE: url(http://cfs.tistory.com/blog/style/template/image/pattern/11.gif); BACKGROUND-COLOR: rgb(255,255,255); MARGIN: 0px auto; FONT: 12px/18px Tahoma; BACKGROUND-POSITION: 0% 0%; COLOR: rgb(85,85,85)" border=0 cellSpacing=5 cellPadding=0><br /> <br /> 
  
  <TR>
    <br /> 
    
    <TD style="BACKGROUND-IMAGE: url(http://cfs.tistory.com/blog/style/template/image/pattern/11.gif); BACKGROUND-COLOR: rgb(255,255,255); MARGIN: 0px; FONT: 12px/18px Tahoma; BACKGROUND-POSITION: 0% 0%; COLOR: rgb(85,85,85)">
      <A style="BORDER-BOTTOM: 1px dashed; COLOR: rgb(0,102,204); TEXT-DECORATION: none" href="http://cfs16.tistory.com/original/30/tistory/2010/07/14/18/26/4c3d82d92b218" rel=lightbox target=_blank><IMG style="BORDER-RIGHT-WIDTH: 0px; BORDER-TOP-WIDTH: 0px; BORDER-BOTTOM-WIDTH: 0px; BORDER-LEFT-WIDTH: 0px" alt="" src="http://cfs16.tistory.com/image/30/tistory/2010/07/14/18/26/4c3d82d92b218" width=300 height=330></A><br /> <P style="TEXT-ALIGN: center; FONT: 11px 돋움, 돋움체; COLOR: rgb(102,102,102)" class=cap1>BJT 회로</P>
    </TD>
    
    <br /> 
    
    <TD style="BACKGROUND-IMAGE: url(http://cfs.tistory.com/blog/style/template/image/pattern/11.gif); BACKGROUND-COLOR: rgb(255,255,255); MARGIN: 0px; FONT: 12px/18px Tahoma; BACKGROUND-POSITION: 0% 0%; COLOR: rgb(85,85,85)">
      <A style="BORDER-BOTTOM: 1px dashed; COLOR: rgb(0,102,204); TEXT-DECORATION: none" href="http://cfile5.uf.tistory.com/original/18528B0E4C3D9B02199695" rel=lightbox target=_blank><IMG style="BORDER-RIGHT-WIDTH: 0px; BORDER-TOP-WIDTH: 0px; BORDER-BOTTOM-WIDTH: 0px; BORDER-LEFT-WIDTH: 0px" alt="" src="http://cfile5.uf.tistory.com/image/18528B0E4C3D9B02199695" width=300 height=330></A><br /> <P style="TEXT-ALIGN: center; FONT: 11px 돋움, 돋움체; COLOR: rgb(102,102,102)" class=cap1>CMOS 회로</P>
    </TD>
  </TR></TABLE>
</DIV>

  
위 그림이 push-pull 출력단을 간단하게 그려본 것이다.  
push-pull 출력 포트는 2개의 TR로 구성된다. 아래쪽의 NPN TR(N-MOS)이 pull을 담당하고, 위쪽의 PNP TR(P-MOS)이 push를 담당한다. 단어의 의미를 생각해 보면 쉽게 이해할 수 있다. NPN TR은 GND쪽으로 끌어 당기는 역할을 하고, PNP TR은 VCC쪽으로 밀어 올리는 역할을 한다.

로직 회로에서는 TR을 switch로 사용한다는 것을 생각해 보면 쉽게 이해할 수 있다.

<DIV style="TEXT-ALIGN: center; CLEAR: both" class="imageblock center">
  <A style="BORDER-BOTTOM: 1px dashed; COLOR: rgb(0,102,204); TEXT-DECORATION: none" href="http://cfs16.tistory.com/original/23/tistory/2010/07/14/18/37/4c3d857715b51" rel=lightbox target=_blank><IMG style="BORDER-RIGHT-WIDTH: 0px; BORDER-TOP-WIDTH: 0px; BORDER-BOTTOM-WIDTH: 0px; BORDER-LEFT-WIDTH: 0px" alt="사용자 삽입 이미지" src="http://cfs16.tistory.com/image/23/tistory/2010/07/14/18/37/4c3d857715b51" width=300 height=330></A><br /> <P style="TEXT-ALIGN: center; FONT: 11px 돋움, 돋움체; COLOR: rgb(102,102,102)" class=cap1>스위치로 치환해보자!</P>
</DIV>두개의 스위치 중 아래쪽 스위치를 ON 시키면 output port는 GND와 바로 연결된다. 즉, Output port를 GND쪽으로 끌어내린 것으로 0V가 출력된다. 반면 위쪽 스위치를 ON 시키면 VCC와 연결되어 high가 출력된다. VCC쪽으로 밀어 올린 것이다.

Push-pull 출력단은 그 자체로 동작한다. 이게 무슨 말이냐 하면&#8230; Output port에 아무것도 연결되어 있지 않더라도 output port의 전압이 의도한 바 대로 움직인다는 뜻이다. Low를 출력할 때엔 0V가 출력되고, high를 출력하면 VCC혹은 VDD가 출력된다. Output port에 아무것도 연결하지 말고 멀티메터나 오실로스코프로 관찰해 보면 출력 전압이 움직이는 것을 볼 수 있다.  
Open collector 혹은 open drain은 이와 다르다.

<DIV style="TEXT-ALIGN: center" class="imageblock dual">
  <br /> <TABLE style="BACKGROUND-IMAGE: url(http://cfs.tistory.com/blog/style/template/image/pattern/11.gif); BACKGROUND-COLOR: rgb(255,255,255); MARGIN: 0px auto; FONT: 12px/18px Tahoma; BACKGROUND-POSITION: 0% 0%; COLOR: rgb(85,85,85)" border=0 cellSpacing=5 cellPadding=0><br /> <br /> 
  
  <TR>
    <br /> 
    
    <TD style="BACKGROUND-IMAGE: url(http://cfs.tistory.com/blog/style/template/image/pattern/11.gif); BACKGROUND-COLOR: rgb(255,255,255); MARGIN: 0px; FONT: 12px/18px Tahoma; BACKGROUND-POSITION: 0% 0%; COLOR: rgb(85,85,85)">
      <A style="BORDER-BOTTOM: 1px dashed; COLOR: rgb(0,102,204); TEXT-DECORATION: none" href="http://cfs16.tistory.com/original/18/tistory/2010/07/14/18/50/4c3d88663a995" rel=lightbox target=_blank><IMG style="BORDER-RIGHT-WIDTH: 0px; BORDER-TOP-WIDTH: 0px; BORDER-BOTTOM-WIDTH: 0px; BORDER-LEFT-WIDTH: 0px" alt="사용자 삽입 이미지" src="http://cfs16.tistory.com/image/18/tistory/2010/07/14/18/50/4c3d88663a995" width=300 height=330></A><br /> <P style="TEXT-ALIGN: center; FONT: 11px 돋움, 돋움체; COLOR: rgb(102,102,102)" class=cap1>Open Collector</P>
    </TD>
    
    <br /> 
    
    <TD style="BACKGROUND-IMAGE: url(http://cfs.tistory.com/blog/style/template/image/pattern/11.gif); BACKGROUND-COLOR: rgb(255,255,255); MARGIN: 0px; FONT: 12px/18px Tahoma; BACKGROUND-POSITION: 0% 0%; COLOR: rgb(85,85,85)">
      <A style="BORDER-BOTTOM: 1px dashed; COLOR: rgb(0,102,204); TEXT-DECORATION: none" href="http://cfs16.tistory.com/original/15/tistory/2010/07/14/18/50/4c3d8865e3111" rel=lightbox target=_blank><IMG style="BORDER-RIGHT-WIDTH: 0px; BORDER-TOP-WIDTH: 0px; BORDER-BOTTOM-WIDTH: 0px; BORDER-LEFT-WIDTH: 0px" alt="사용자 삽입 이미지" src="http://cfs16.tistory.com/image/15/tistory/2010/07/14/18/50/4c3d8865e3111" width=300 height=330></A><br /> <P style="TEXT-ALIGN: center; FONT: 11px 돋움, 돋움체; COLOR: rgb(102,102,102)" class=cap1>Open Drain</P>
    </TD>
  </TR></TABLE>
</DIV>이름 그대로 collector 혹은 drain 핀이 외부로 노출(open)되어 있다. Push-pull 출력단과 달리 밀어올려주는(PUSH) 위쪽 절반이 없다. 더군다나 VCC나 VDD와도 전혀 연결되어 있지 않다.<SPAN class=Apple-converted-space>&nbsp;</SPAN>

<SPAN style="COLOR: rgb(255,0,0)">반쪽짜리 미완성</SPAN><SPAN class=Apple-converted-space>&nbsp;</SPAN>회로인 것이다.  
다시 스위치 모델을 생각하면서 생각해 보자. NPN TR이나 N-MOS가 ON 되었을 경우에는 Output port가 GND로 당겨지므로 0V 출력이 나가게 된다. 이 반쪽은 잘 동작한다(엄밀히 따지면 또 그렇지도 않지만 설명을 위해^^). 반면 NPN TR이나 N-MOS가 OFF되었을 경우 Output port는 그냥 무주공산으로 떠버리게 된다. 소위 Unknown state가 된다. 0V도 아니고 VCC나 VDD도 아닌 상태.

Open drain 출력단은 말 그대로 미완성 회로다. 이 상태 만으로는 제대로 동작하지 않는다. 외부에 부가 회로가 필요하다. 그러면 왜 이렇게 사용하는 것일까? 그것은 바로<SPAN class=Apple-converted-space>&nbsp;</SPAN><SPAN style="COLOR: rgb(255,0,0)">입맛에 맞게 알아서 꾸며 쓰기</SPAN><SPAN class=Apple-converted-space>&nbsp;</SPAN>위해서이다.  
Open drain 출력단이 필요한 경우는 여러가지가 있다. 대표적인 예로 level converter(level shifer), bus 구성 등이 있다.

Level converter로 사용하는 예를 살펴보자

<DIV style="TEXT-ALIGN: center; CLEAR: both" class="imageblock center">
  <A style="BORDER-BOTTOM: 1px dashed; COLOR: rgb(0,102,204); TEXT-DECORATION: none" href="http://cfs16.tistory.com/original/5/tistory/2010/07/14/18/59/4c3d8a959507b" rel=lightbox target=_blank><IMG style="BORDER-RIGHT-WIDTH: 0px; BORDER-TOP-WIDTH: 0px; BORDER-BOTTOM-WIDTH: 0px; BORDER-LEFT-WIDTH: 0px" alt="사용자 삽입 이미지" src="http://cfs16.tistory.com/image/5/tistory/2010/07/14/18/59/4c3d8a959507b" width=410 height=330></A><br /> <P style="TEXT-ALIGN: center; FONT: 11px 돋움, 돋움체; COLOR: rgb(102,102,102)" class=cap1>VDD != V_EXT</P>
</DIV>위 그림에서 open drain 출력의 Output Port를 오른쪽에 있는 다른 장치의 입력 포트에 연결하려고 한다. 간단하게 왼쪽의 큰 상자를 MCU라 생각하고 오른쪽의 작은 상자를 센서 칩이라 생각해 보자. MCU가 사용하는 VDD는 3.3V이다. 센서 칩이 사용하는 전원(V_EXT)는 5V다. 이처럼 칩들이 사용하는 전원 전압이 다른 경우 바로 연결하면 문제가 발생할 수 있다. 이를 해결하는 한가지 수단으로 open drain 혹은 open collector가 사용될 수 있다. 위 회로처럼 외부에 풀업 저항(pull-up resisitor)을 하나 달아주게 되면 level shifter가 구성된다.

  
MCU 내부의 N-MOS 스위치가 ON되었을 경우 Output Port는 0V로 당겨지므로(PULL) low 출력이 나가게 된다. 이 경우는 push-pull 출력단과 동일하다. 반면 N-MOS 스위치가 OFF 되었을 경우 Output port가 unknown 상태가 되는 대신 외부 풀업저항에 의해 V_EXT로 묶여 올라가게 되는 것이다.<SPAN class=Apple-converted-space>&nbsp;</SPAN><SPAN style="TEXT-DECORATION: underline">이것을 소극적인 push라고 생각하면 여러가지로 도움이 된다</SPAN>. 반면 push-pull 출력단의 위쪽 스위치는 적극적인 push인 샘이다.  
level shifter를 구성할 때 사용하는 풀업저항의 크기는 회로 성격(TTL회로냐 CMOS회로냐)과 전원 전압에 따라 달라진다. 전류의 크기와 소비 전력을 고려해서 구해야 한다.

Level shifter를 이처럼 간단하게 구성할 수도 있지만 실상은 조금 복잡하다. TTL 로직과 달리 CMOS 로직은 정전기에 약하다. 때문에 정전기 보호 회로가 IO 핀마다 달려있는데, 가장 기본적인 정전기 보호 회로는 아래 그림과 같이 다이오드로 구성된다.

<DIV style="TEXT-ALIGN: center; CLEAR: both" class="imageblock center">
  <A style="BORDER-BOTTOM: 1px dashed; COLOR: rgb(0,102,204); TEXT-DECORATION: none" href="http://cfs16.tistory.com/original/12/tistory/2010/07/14/19/13/4c3d8dba35487" rel=lightbox target=_blank><IMG style="BORDER-RIGHT-WIDTH: 0px; BORDER-TOP-WIDTH: 0px; BORDER-BOTTOM-WIDTH: 0px; BORDER-LEFT-WIDTH: 0px" alt="사용자 삽입 이미지" src="http://cfs16.tistory.com/image/12/tistory/2010/07/14/19/13/4c3d8dba35487" width=300 height=330></A><br /> <P style="TEXT-ALIGN: center; FONT: 11px 돋움, 돋움체; COLOR: rgb(102,102,102)" class=cap1>다이오드로 구성된 ESD</P>
</DIV>위 그림 처럼 2개의 다이오드가 출력핀 바로 안쪽에 위치해서 GND와 VDD 범위를 넘어서는 전하(extra charge)는 다이오드를 통해 방출(discharge)시켜 버리는 것이다. 정전기는 전압은 높지만 전하(전기 에너지)는 작기 때문에 이처럼 그냥 다이오드로 방출시켜버리면 내부 회로를 보호할 수 있다.

  
ESD(Electro-Static Discharge) 회로가 level shifter에 미치는 영향은 VDD가 V\_EXT보다 낮을 때 나타난다. 위에서 살펴본 예 처럼 V\_EXT가 높으면 N-MOS가 OFF되어 R에 의해 소극적으로 push 되더라도 Output Port의 전압은 VDD를 넘어설 수 없다. 넘어선 전압만큼 다이오드를 통해 방출되어 버리기 때문이다. 더군다나 이렇게 방출되는 (V_EXT &#8211; VDD)만큼의 전기 에너지는 정전기 보호를 위해 설계된 다이오드의 용량을 초과하기 때문에 ESD 보호용 다이오드를 파괴시켜 버린다. MCU의 datasheet를 보다 보면 Absolute Rating 항목을 발견할 수 있고 여기에 IO 핀들에 인가될 수 있는 최대 전압이 명시되어 있다. 보통은 VDD+0.3V를 최대 전압으로 잡는다. ESD 보호용 다이오드의 forward voltage인 0.3V를 넘어서는 전압이 인가되면 다이오드를 통해 그 에너지가 흘러가게되고 결국 다이오드가 파괴된다. 운 좋으면 해당 핀만 못쓰게 되고, 운나쁘면 그냥 전체가 다 먹통이&nbsp; 된다.  
정리하면 level shifter 목적으로 open drain 출력단을 사용하려면 ESD 보호 다이오드가 없는 칩을 사용하지 않는 이상 높은전압->낮은전압 변환만 사용해야만 한다는 것이다. 물론 CMOS 로직 칩에 ESD 보호 회로가 안달린 경우는 현실세계엔 없다 ^^; (있기는 하다. 학부다닐때 학교내에 있는 FAB에서 실험용으로 만든 CMOS 칩이 있었고, ESD가 안달려 있었다. 그래서 그 칩을 다루려면 손목에<SPAN class=Apple-converted-space>&nbsp;</SPAN><A style="BORDER-BOTTOM: 1px dashed; COLOR: rgb(0,102,204); TEXT-DECORATION: none" title="[http://www.google.co.kr/images?q=ESD+band&hl=ko&newwindow=1&rlz=1B3GGLL\_koKR364KR364&prmd=livnk&source=lnms&tbs=isch:1&ei=sJg9TIiZK8vJce6Q5aIB&sa=X&oi=mode\_link&ct=mode&ved=0CB0Q\_AU]로 이동합니다." href="http://www.google.co.kr/images?q=ESD+band&hl=ko&newwindow=1&rlz=1B3GGLL\_koKR364KR364&prmd=livnk&source=lnms&tbs=isch:1&ei=sJg9TIiZK8vJce6Q5aIB&sa=X&oi=mode\_link&ct=mode&ved=0CB0Q\_AU" target=_blank>접지밴드</A><SPAN class=Apple-converted-space>&nbsp;</SPAN>두르고 작업해야만 했다. 그럼에도 불구하고 숱하게 날려먹었다. 그만큼 CMOS는 정전기에 약하다.)

Open drain을 사용하는 두번째 예로 bus 구성을 살펴보자. bus 구성이라 함은 다수의 칩이 모두 output으로 포트를 공유하는 경우를 말한다. 앞서 올렸었던<SPAN class=Apple-converted-space>&nbsp;</SPAN><A style="BORDER-BOTTOM: 1px dashed; COLOR: rgb(0,102,204); TEXT-DECORATION: none" href="http://irmus.tistory.com/75">2010/07/12 &#8211; myGyro300SPI 3개 연결하기</A><SPAN class=Apple-converted-space>&nbsp;</SPAN>포스팅을 보면 3개의 myGyro300SPI를 SPI 버스에 무작정 연결시켜 놓고 사용한다. SPI 버스를 구성하는 CLK, MOSI, CS는 master인 MCU에서 output하고 myGyro300SPI는 input으로 쓰이기 때문에 문제될 것이 없다. 반면 MISO 핀은 좀 다르다. myGyro300SPI가 모두 MISO 핀을 output으로 사용하고 있다. 이 경우가 왜 문제가 되는지는 좀만 생각해 보면 간단하다. 만약 myGyro300SPI의 MISO(DOUT)핀이 push-pull 출력단이라면 각 핀들이 0V 혹은 VDD_IO를<SPAN class=Apple-converted-space>&nbsp;</SPAN><SPAN style="COLOR: rgb(255,0,0)">적극적</SPAN>으로 출력한다. 즉 어떤 녀석은 0V를 출력할 수도 있고 어떤 녀석은 3.3V를 출력할 수도 있다는 뜻이다. 이렇게 적극적으로 push/pull 하는 output port들이 서로 쫑나게 되면 회로가 타버리게 된다. 그래서<SPAN class=Apple-converted-space>&nbsp;</SPAN><SPAN style="COLOR: rgb(255,0,0)">소극적으로 push하는 open-drain 출력단</SPAN>이 쓰인다. Open-drain 출력단에서 HIGH 출력을 내보내고 있을 때, 즉 N-MOS가 OFF되어 있을 때에는 unknown 상태로 된다. 우리말로는 의지박약 상태로 번역하고 싶다. 이 상태에는 아무도 안 건드리면 VDD_IO를 가질 수 있지만 옆에서 누가 &#8220;나 0V 할거야&#8221; 라고 강하게 주장(pull)하면 그쪽으로 군소리 없이 따라가게 된다. A형 혈액형이다.

이처럼 다수의 output port를 서로 묶어서 버스로 구성할 때에는 open drain 출력단이 필요하다. 여기서 잠깐 의혹이 하나 생긴다.<SPAN class=Apple-converted-space>&nbsp;</SPAN><A style="BORDER-BOTTOM: 1px dashed; COLOR: rgb(0,102,204); TEXT-DECORATION: none" href="http://irmus.tistory.com/75">2010/07/12 &#8211; myGyro300SPI 3개 연결하기</A><SPAN class=Apple-converted-space>&nbsp;</SPAN>글의 회로도를 보면 어디에도 풀업저항이 안보인다. Open drain은 반쪽짜리 미완성이므로 풀업저항이 꼭 필요하다고 설명했는데 왜이런걸까? 해답은 ADIS16100의 DOUT 핀 내부에 풀업저항이 내장되어 있기 때문이다. 데이터쉬트상에 따로 명기되어 있지는 않지만 풀업 저항이 내장되어 있다고 생각할 수 있다. 그걸 어떻게 아느냐고한다면&#8230; 몇가지 실험을 통해서 유추한것 뿐이다 ^^

또다른 예로 I2C 버스를 생각해 봐도 된다. I2C는 완전한 open drain 출력단으로 풀업 저항을 외부에 꼭 달아줘야만 한다. I2C는 버스 구성 뿐만 아니라 bi-directional 포트이기에 풀업저항을 내장할 수가 없고 스팩에도 그렇게 정해져 있다.

지금까지 push-pull과 open collector, open drain 출력단에 대해 살펴봤다. TTL로직과 CMOS 로직의 차이도 아주 쪼금 다루긴 했지만 많이 부족한 내용이다. 특히 TTL 로직의 경우 fan-in과 fan-out까지 고려해야 한다. open collector의 풀업저항 계산할 때 fan-in이 중요하다.<SPAN class=Apple-converted-space>&nbsp;</SPAN>  
칩설계를 전공한 것도 아니고 십년도 훨씬 지난 학부시절 전자회로 수업들은 지식으로 떠들다 보니 말만 장황하고 부족한 내용도 많은 글이 됐다. 어디까지나 초보 입문용으로 작성된 글이며, 설명된 내용들 외에도 중요한 포인트 들이 많이 있다는 것을 염두에 두도록 하자.</SPAN></SPAN>