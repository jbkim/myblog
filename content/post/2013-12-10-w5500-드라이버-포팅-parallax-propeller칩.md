---
title: 'W5500 드라이버 포팅: Parallax Propeller칩'
author: openmicrolab
type: post
date: 2013-12-10T02:54:02+00:00
url: /w5500-드라이버-포팅-parallax-propeller칩/
dsq_thread_id:
  - "2090820253"
categories:
  - Open Source Hardware
  - Development
  - Network
  - Uncategorized
tags:
  - parallax
  - Propeller
  - W5500
  - WIZ550io

---
<a href="http://parallax.com/" target="_blank">Parrallax</a>는 미국의 펩리스 반도체 회사이다. 이 회사의 칩은 <a href="http://parallax.com/microcontrollers/propeller" target="_blank">Propeller</a>인데 이 칩은 특이하게도 내부에 8개의 프로세어 코아가 있어서 병렬처리가 가능하다. 이 8개의 코아를 COG라고 부르는데, 아래 블럭다이아그램 처럼 내부에 각각 프로세서, RAM, 레지스터, 카운터 등이 있고 이 COG가 외부에 나와 있는 I/O를 공유한다. 그리고 각각의 COG를 제어하는 HUB가 있어서 각각의 COG각 언제 I/O를 access할지를 결정한다.

[<img loading="lazy" class="alignnone size-full wp-image-2736" alt="parallax_propeller" src="/images/2013/12/parallax_propeller.png" width="921" height="570" srcset="/images/2013/12/parallax_propeller.png 921w, /images/2013/12/parallax_propeller-300x185.png 300w" sizes="(max-width: 921px) 100vw, 921px" />][1]

Propeller칩을 프로그래밍하게 위해서는 어셈블러, SPIN이라는 언어로 프로그래밍이 가능하며, 최근에는 C 컴파일러가 지원이어서 C로도 프로그래밍이 가능하지만 코드사이즈나 성능이슈로 대부분의 코드는 어셈블러나 SPIN으로 만들어져 있다.

데이터 시트 및 메뉴얼은 다음 링크에서 다운로드&#8230;

[wpdm\_file id=7]  [wpdm\_file id=8]

<a href="http://wizwiki.net/wiki/doku.php?id=products:w5500:start" target="_blank">W5500</a>칩의 드라이버를 포팅하기 위해 사용한 보드는 <a href="http://parallax.com/product/32910" target="_blank">Propeller Activity Board</a>인데, 이 보드에 있는 브레드보드에 <a href="http://wizwiki.net/wiki/doku.php?id=products:wiz550io:start" target="_blank">WIZ550io</a>를 꼽고 와이어링을 통해 Propeller칩과 연결을 했다. 연결되는 방식은 SPI 신호, 리셋 신호 및 전원 신호만 결하면 되므로 간단하다.

<p style="text-align: center;">
  <a href="/images/2013/12/Propeller_WIZ550io.jpg"><img loading="lazy" class="size-full wp-image-2737 aligncenter" alt="Propeller_WIZ550io" src="/images/2013/12/Propeller_WIZ550io.jpg" width="636" height="562" srcset="/images/2013/12/Propeller_WIZ550io.jpg 636w, /images/2013/12/Propeller_WIZ550io-300x265.jpg 300w" sizes="(max-width: 636px) 100vw, 636px" /></a>
</p>

포팅한 코드는 Mike G라는 사람이 W5200으로 만든 코드를 포팅을 했는데, 이 코드는 SPI 인터페이스가 어셈블러로 되어있어서 이것을 일단 SPIN 랭귀지로 수정했다. W5500에서는 SPI 포맷 및 메모리 맵이 바뀌어서 W5500을 read, write하는 함수들 역시 수정을 했다.  수정된 코드가 제대로 동작하는지 확인을 하기위해 TCPMultiSocketServer 프로그램(간단한 웹서버 프로그램) 코드와 같이 컴파일을 해서 돌리니 잘 동작한다.

관련된 모든 코드는 github에 오픈: <a title="W5500 porting on Propeller" href="https://github.com/jbkim/Parallax_W5500" target="_blank">https://github.com/jbkim/Parallax_W5500</a>

 [1]: /images/2013/12/parallax_propeller.png