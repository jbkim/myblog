---
title: STM8S-DISCOVERY 보드와 WIZ820io의 연결
author: openmicrolab
type: post
date: 2011-11-04T11:18:34+00:00
url: /stm8s-discovery-보드와-wiz820io의-연결/
dsq_thread_id:
  - "1179638142"
categories:
  - Wiznet
tags:
  - Loopback
  - wiz820io
  - Twitter
  - dns
  - STM8S

---
ST마이크로의 8비트 MCU EVB인 STM8S-Discovery 보드에 Wiznet의 WIZ820io를 SPI로 연결하여 테스트를 해보았다.

<p style="margin: 0px;">
  <img loading="lazy" class="aligncenter" src="/images/1/cfile2.uf.193F25424EB3C8CB2DBE49.jpg" alt="" width="413" height="298" />
</p>

STM8S-DISCOVERY 관련자료 : <http://www.st.com/internet/evalboard/product/247087.jsp>  
STM8S-DISCOVERY보드의 메뉴얼;

<p style="margin: 0px;">
  <a class="aligncenter" href="/images/1/cfile7.uf.185721394EB3C4731FDE54.pdf">cfile7.uf.185721394EB3C4731FDE54.pdf</a>WIZ820io 관련 자료 : <a href="http://www.wiznet.co.kr/wiz820io">http://www.wiznet.co.kr/wiz820io</a>
</p>

**1. 하드웨어 연결**  
SPI 신호들은 CN1, CN2에 나와 있는 SPI 신호에 연결하고, nSS, nINT, nRESET, PWDN 신호들은 각각 STM8S의 GPIOs(PA4, PA5, PA3 and PA6)에 연결이 된다.

<p style="margin: 0px;">
  <img loading="lazy" class="aligncenter" src="/images/1/cfile25.uf.170ABB3C4EB3C578357278.png" alt="" width="449" height="357" />
</p>

**2. Firmware  
** 컴파일러는 <a title="[http://www.cosmic-software.com/]로 이동합니다." href="http://www.cosmic-software.com/" target="_blank" rel="noopener noreferrer">Cosmic</a>사의 <a title="[http://www.cosmic-software.com/stm8.php]로 이동합니다." href="http://www.cosmic-software.com/stm8.php" target="_blank" rel="noopener noreferrer">CXSTM8 compiler</a>와 ST 홈페이지에서 다운로드 받을 수 있는 STVD를 사용한다. CXSTM8 compiler는 등록을 하면 일정기간 사용이 가능하다.

<p style="margin: 0px;">
  <img loading="lazy" class="aligncenter" src="/images/1/cfile23.uf.196DFD394EB3C69E0C9D3F.png" alt="" width="575" height="410" />
</p>

**3. Test  
** STM8S의 Application Note인 RS232 communications with a terminal using the STM8S-DISCOVERY를 참고로 시리얼 터미널 기반의 application을 만들어 보았다. 기존의 메뉴에 다음과 같이 네트웍을 설정하고 확인하는 메뉴, TCP/UDP loopback, DNS, Twitter 기능을 테스트 할 수 있는 기능을 추가했다.

<p style="margin: 0px;">
  <img loading="lazy" class="aligncenter" src="/images/1/cfile23.uf.163249444EB3C7900D9BC6.png" alt="" width="386" height="245" />
</p>

Application Note:

<p style="margin: 0px;">
  <a class="aligncenter" href="/images/1/cfile7.uf.130B70444EB3C74F2E6C98.pdf">cfile7.uf.130B70444EB3C74F2E6C98.pdf</a>
</p>