---
title: LPC810 ARM CortexM0+ Project -1
author: openmicrolab
type: post
date: 2013-09-09T07:22:03+00:00
url: /lpc810-arm-cortexm0-project-1/
featured_image: /wp-content/uploads/2013/09/LPC810_Board-100x100.jpg
dsq_thread_id:
  - "1739412163"
categories:
  - ARM
  - Open Source Hardware
tags:
  - CortexM0
  - adafruit
  - LPC810
  - ARM CortexM0+
  - LPC810 Mini Starter Pack

---
### Project Description

이 프로젝트의 목적은 가장 작은 MCU에 Ethernet connectivity를 구현하는 것이다. 아마 아래 그림과 같은 형태가 될것이다.

[<img loading="lazy" class=" wp-image-2651 alignnone" alt="lpc810_ethernet" src="/images/2013/09/lpc810_ethernet.jpg" width="717" height="484" srcset="/images/2013/09/lpc810_ethernet.jpg 1024w, /images/2013/09/lpc810_ethernet-300x202.jpg 300w" sizes="(max-width: 717px) 100vw, 717px" />][1]

### CortexMo+

NXP에서 출시한 LPC800시리즈는 ARM사의 CortexM0+ 시리즈의 칩이다. ARM의 소개 페이지에 있는 것 처럼 CortexM0와 마찬가지로 8, 16비트 시장을 타겟으로 하고 있다. CortexM0와 비교해서는 파워소모를 더 줄였고 성능은 더 높인 버젼이라고 이해하면 될 듯 하다. <a href="http://deltas.blog.com/2013/03/13/arm-cortex-m0-vs-msp430-or-are-m0-based-devices-really-16-bit-mcu-replacements-2/" target="_blank">TI의 MSP430과 비교를 한 사이트</a>도 있는데, GPIO만 적을뿐 가격, 파워 소모, 성능등 모든 면에서 우월하다.

### LPC810

LPC800 시리즈중 눈길을 끄는 칩은 8핀 DIP패키지인 <a href="http://www.nxp.com/products/microcontrollers/cortex_m0_m0/LPC810M021FN8.html" target="_blank">LPC810</a> 이다.

<p style="font-size: 13px;">
  <img loading="lazy" title="lpc800_dip8.jpg" alt="Lpc800 dip8" src="/images/2013/09/lpc800_dip8.jpg" width="320" height="273" border="0" />
</p>

<p style="font-size: 13px;">
  이 패키지의 내부 구조는 아래 그림과 같다. 전원핀 6, 7번을 제외하면 나머지 핀들은 GPIO와 다른 기능이 multiplex되어 있어서 칩의 핀수를 줄일 수 있다. 더구나 내부 RC발진 회로덕분에 외부에 크리스탈 또는 오실레이터를 연결하지 않아도 된다.
</p>

<p style="font-size: 13px;">
  <a href="/images/2013/09/LPC810_Pin.png"><img loading="lazy" class="size-full wp-image-2629 alignnone" alt="LPC810_Pin" src="/images/2013/09/LPC810_Pin.png" width="619" height="187" srcset="/images/2013/09/LPC810_Pin.png 619w, /images/2013/09/LPC810_Pin-300x90.png 300w" sizes="(max-width: 619px) 100vw, 619px" /></a>
</p>

<p style="font-size: 13px;">
  LPC810 시리즈는 아래 그림과 같이 메모리 용량에 따라 DIP8, TSSOP16, SO20, TSSOP20등의 패키지가 존재한다.
</p>

<p style="font-size: 13px;">
  <img loading="lazy" title="LPC810_Ordering.png" alt="LPC810 Ordering" src="/images/2013/09/LPC810_Ordering.png" width="491" height="293" border="0" />
</p>

### 회로도

<p style="font-size: 13px;">
  <a href="/images/2013/09/LPC810_Sch.jpg"><img loading="lazy" class=" wp-image-2630 alignnone" alt="LPC810_Sch" src="/images/2013/09/LPC810_Sch-1024x561.jpg" width="819" height="449" srcset="/images/2013/09/LPC810_Sch-1024x561.jpg 1024w, /images/2013/09/LPC810_Sch-300x164.jpg 300w" sizes="(max-width: 819px) 100vw, 819px" /></a>
</p>

일단 간단한 동작확인을 위해 Ardafruit에서 <a href="http://www.adafruit.com/products/1336" target="_blank">LPC810 Mini Starter Pack</a>을 구매하고 <a href="http://learn.adafruit.com/assets/6787" target="_blank">Adafruit의 회로</a>를 참고해서 위와 같은 회로를 구성하였다. Adafruit의 회로는 초보자를 위해 Fritzing(<a href="http://openmicrolab.com/?s=fritzing" target="_blank">이 툴 관련 이전 블로그의 글들</a>)을 이용해서 그려져 있는데 사실 엔지니어가 보기에는 회로도가 더 편하다. 암튼 안정적인 동작을 위해 난 리셋 회로를 추가하고 편의를 위해 ISP에 핀 헤더를 달았다. P0_2에는 LED가 달려있으며, MCP1700 레귤레이터를 통해 5V가 3.3V로 변환되어 칩에 입력이 된다.

### 프로그래밍

요즘 나오는 칩들이 거의 모두다 그렇지만 이 칩도 내부 ROM에 bootloader가 있고,  ISP(In System Programming)기능을 지원한다. 즉 UART를 통해서 내부 Flash의 업데이트가 가능하다.  그리고 NXP에서 제공하는 개발 환경인 LPCXpresso는 이클립스 기반이라서 Win, MAC, Linux를 모두 지원한다.  Adafruit에서 소개하는 페이지에는 Windows기반에서 설명을 하는데 난 MAC  환경이라서 OS X에서 개발 환경을 구축하였다. LPCXpresso를 다운받으려면 <a href="http://lpcxpresso.code-red-tech.com/LPCXpresso/" target="_blank">http://lpcxpresso.code-red-tech.com/LPCXpresso/</a> 여기에 사용자 등록을 해야 다운로드가 가능하다. 문제는  MAC용 <a href="http://www.flashmagictool.com/" target="_blank">Falsh Magic</a>에서 아직 LPC800시리즈를 지원하지 않아서 <a href="http://lpc21isp.sourceforge.net/" target="_blank">lpc2isp</a>를 사용해야 한다.

  * LPCXpresso에 프로젝트 등록 : 이 내용은 Adafruit에 자세히 나와 있으니 <a href="http://learn.adafruit.com/getting-started-with-the-lpc810/importing-a-project" target="_blank">이곳을</a> 참고. 간단히 설명하면  코드를 <a href="https://github.com/microbuilder/LPC810_CodeBase" target="_blank">Github</a>에서 ZIP 형태로 다운로드해서  받아서 LPCXpresso에서 Import Project를 하면 된다.
  * PL2303드라이버: Adafruit의 <a href="http://www.adafruit.com/products/954" target="_blank">USB to TTL Serial Cable</a> 에서 설명하는 Prolific 드라이버를 설치했으나 MAC 에서 인식이 되지 않아 인터넷에서 <a href="http://www.prolific.com.tw/US/ShowProduct.aspx?p_id=229&pcid=41" target="_blank">다른 드라이버</a>를 찾아서 인식시켰다. [wpdm_file id=3]
  * Mac에서 시리얼 포트가 잡혔는지 확인하기: ls /dev/tty.*
  * Flash Magic 대신 lpc2isp사용하기: <a href="http://lpc21isp.sourceforge.net/" target="_blank">http://lpc21isp.sourceforge.net/</a>에서 소스를 다운로드 받아서 gcc 로 컴파일 한다. 단 make 파일에서 CFLAG에 -static옵션을 빼야지 제대로 컴파일이 된다.

[<img loading="lazy" class="size-full wp-image-2645 alignnone" alt="lpc21isp" src="/images/2013/09/lpc21isp.png" width="609" height="520" srcset="/images/2013/09/lpc21isp.png 609w, /images/2013/09/lpc21isp-300x256.png 300w" sizes="(max-width: 609px) 100vw, 609px" />][2]

  * lpc2isp 사용법은 &#8220;lpc21isp hex-file명 serial-port baud-rate clock of MCU(in Khz단위)&#8221;이다 여기서 마지막 파라미터인 MCU의 clock을 Khz단위로 넣는 것이 중요하다.  즉: **./lpc21isp LPC810_CodeBase.hex usbserial 115200 12000** 을 입력하면 아래 그림과 같이 제대로 flash가 write 된다.

[<img loading="lazy" class="size-full wp-image-2647 alignnone" alt="lpc2isp" src="/images/2013/09/lpc2isp.png" width="813" height="473" srcset="/images/2013/09/lpc2isp.png 813w, /images/2013/09/lpc2isp-300x174.png 300w" sizes="(max-width: 813px) 100vw, 813px" />][3]

위와 같이 프로그래밍 끝나면,  점퍼를 제거하고 리셋 버튼을 누르면 코드가 동작을 한다. 아래 그림은 LED를 깜박이는 코드를 로드&#8230;.

[<img loading="lazy" alt="LPC810_Board" src="/images/2013/09/LPC810_Board-1024x752.jpg" width="717" height="526" />][4]

 [1]: /images/2013/09/lpc810_ethernet.jpg
 [2]: /images/2013/09/lpc21isp.png
 [3]: /images/2013/09/lpc2isp.png
 [4]: /images/2013/09/LPC810_Board.jpg