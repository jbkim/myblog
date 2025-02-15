---
title: BBC micro:bit 분석
author: openmicrolab
type: post
date: 2016-09-11T14:45:36+00:00
url: /bbc-microbit-분석-1/
categories:
  - ARM
  - mbed
  - Microbit
  - Infomation
  - Development
tags:
  - mbed
  - BBC micro:bit
  - microbit

---
<p class="p1">
  <span class="s1">BBC <a href="http://microbit.co.uk/"><span class="s2">micro:bit</span></a></span>는 영국에서 컴퓨터 교육용으로 디자인된 마이크로컨트롤러 보드이다<span class="s1">.</span>
</p>

<p class="p1">
  <img loading="lazy" class="alignnone wp-image-3744" src="http://res.cloudinary.com/openmicrolab/image/upload/v1473602467/MicroBit_board_xcvrdp.jpg" width="472" height="364" />
</p>

<p class="p1">
  <strong>개발에 참여한 파트너사들</strong>
</p>

<ul class="ul1">
  <li class="li3">
    <span class="s2">Microsoft</span> – Block Editor, Touch Develop 개발
  </li>
  <li class="li3">
    <a href="https://lancaster-university.github.io/microbit-docs/" target="_blank"><span class="s2">Lancaster University</span> – Device runtime개발</a>
  </li>
  <li class="li3">
    <span class="s2">Farnell element14</span> – 디바이스 생산
  </li>
  <li class="li3">
    <a href="https://www.nordicsemi.com/eng/Products/Bluetooth-low-energy/nRF51822" target="_blank"><span class="s2">Nordic Semiconductor</span> – MCU 제공</a>
  </li>
  <li class="li3">
    <span class="s2">NXP Semiconductors</span> – USB인터테이스 칩 및 센서 칩제공
  </li>
  <li class="li3">
    <span class="s2">ARM Holdings</span> – <a href="https://developer.mbed.org/" target="_blank">mbed</a> 하드웨어, 컴파일러 서비스
  </li>
  <li class="li3">
    <a href="https://www.techwillsaveus.com/" target="_blank"><span class="s2">Technology Will Save Us</span> – 하드웨어 디바이스 개발</a>
  </li>
  <li class="li3">
    <a href="http://www.samsung.com/uk/microbit/" target="_blank"><span class="s2">Samsung</span> – 안드로이드 앱 개발</a>
  </li>
  <li class="li3">
    <a href="https://sciencescope.uk/" target="_blank">ScienceScope</a> –iOS앱 개발
  </li>
  <li class="li3">
    <span class="s2">Python Software Foundation</span> – <a href="https://en.wikipedia.org/wiki/MicroPython"><span class="s2">MicroPython</span></a> 제공, 웹기반 파이썬 에디터 개발
  </li>
  <li class="li3">
    <a href="https://www.bluetooth.com/" target="_blank">Bluetooth SIG</a> &#8211; Developed the custom Bluetooth LE profile.
  </li>
</ul>

<p class="p1">
  <strong>하드웨어</strong>
</p>

<p class="p1">
  <img loading="lazy" class="alignnone wp-image-3745" src="http://res.cloudinary.com/openmicrolab/image/upload/v1473602504/rxubgeld_nw7b6q.png" width="973" height="547" />
</p>

<ul class="ul1">
  <li class="li2">
    <span class="s1">메인</span> MCU: ARM CortexM0 <span class="s1">코어에</span> <span class="s1">블루투스</span> LE<span class="s1">가</span> <span class="s1">내장된</span> <span class="s1">노르딕사의</span> nRF51822 (256KB flash, 16KB SRAM)
  </li>
  <li class="li2">
    <span class="s1">인터테이스</span> <span class="s1">칩</span>: USB 2.0 OTG<span class="s1">가</span> <span class="s1">내장된</span> NXP<span class="s1">의</span> KL26Z (CortexM0+)<span class="s1">가</span> DAPLink를 제공하여, 가상 USB 플래시 드라이브를 <span class="s1">제공해서 펌웨어 업데이트를 가능하게 하며</span>, USB <span class="s1">파워를</span> <span class="s1">받아서</span> <span class="s1">전압</span> <span class="s1">레귤레이터의</span> <span class="s1">역할</span>. <a href="http://openmicrolab.com/cmsis-dap-%EB%9E%80/" target="_blank">관련 포스팅</a>
  </li>
  <li class="li2">
    3<span class="s1">축</span> <span class="s1">가속도</span> <span class="s1">칩</span>: NXP MMA8652, <span class="s1">메인</span> MCU<span class="s1">와</span> I2C<span class="s1">로</span> <span class="s1">연결</span>
  </li>
  <li class="li2">
    3<span class="s1">축</span> <span class="s1">지자기센서</span> <span class="s1">칩</span>: NXP MAG3110, <span class="s1">메인</span> MCU<span class="s1">와</span> I2C<span class="s1">로</span> <span class="s1">연결</span>
  </li>
  <li class="li2">
    5&#215;5 LED 어레이
  </li>
  <li class="li2">
    2개의 버튼
  </li>
</ul>

<p class="p1">
  <strong>핀아웃</strong>
</p>

<p class="p1">
  <img loading="lazy" class="alignnone wp-image-3751" src="http://res.cloudinary.com/openmicrolab/image/upload/v1473604929/microbit_pinout_vatsl4.png" width="547" height="461" />
</p>

<p class="p1">
  <a href="https://www.microbit.co.uk/create-code" target="_blank"><strong>소프트웨어</strong></a>
</p>

<p class="p1">
  모두다 브라우저기반의 컴파일러를 제공하며, 난이도에 따라 아래 그림 처럼 3가지로 나뉠 수 있다.
</p>

<p class="p1">
  <img loading="lazy" class="alignnone wp-image-3748" src="http://res.cloudinary.com/openmicrolab/image/upload/v1473603042/hwbxnjaw_om9xgm.png" width="638" height="249" />
</p>

<ul class="ul1">
  <li class="li5">
    CodeKingdoms<span class="s5"> &#8211; </span><span class="s6">자바스크립트</span>
  </li>
  <li class="li3">
    Microsoft Block Editor &#8211; <a href="https://en.wikipedia.org/wiki/Blockly"><span class="s2">Blockly</span></a>
  </li>
  <li class="li5">
    <span class="s5">Microsoft <a href="https://www.touchdevelop.com/microbit" target="_blank"><span class="s2">TouchDevelop</span></a></span>
  </li>
  <li class="li3">
    MicroPython
  </li>
  <li class="li3">
    <a href="https://developer.mbed.org/teams/microbit/" target="_blank"> mbed에서 사용하기</a>
  </li>
  <li class="li3">
    <a href="http://www.espruino.com/MicroBit" target="_blank">Espruino에서 사용하기</a>
  </li>
</ul>

**아키텍처**

<img loading="lazy" class="alignnone wp-image-3747" src="http://res.cloudinary.com/openmicrolab/image/upload/c_scale,w_576/v1473602763/Architecture-768x432_q9tqcf.png" width="576" height="304" /> 

**기타**

  * <a href="https://www.mbed.com/en/development/hardware/prototyping-production/daplink/daplink-on-kl26z/#Updating_your_DAPLink_firmware" target="_blank">DAPLink펌웨어 업데이트 하기</a>
  * <a href="https://developer.mbed.org/platforms/Microbit/#firmware" target="_blank">mbed microbit library</a>
  * <a href="https://www.microbit.co.uk/open_source#" target="_blank">Microbit 오픈소스</a>
  * <a href="https://lancaster-university.github.io/microbit-docs/offline-toolchains/" target="_blank">오프라인에서 Microbit 컴파일하고 다운로드하기</a>

**관련자료**

  * <a href="https://www.bluetooth.com/news-events/bluetooth-events/webinars" target="_blank">Bluetooth SIG에서 제공하는 4부작 웨비나</a> : 주로 BT관련 내용이 많다.
  * <a href="http://bluetooth-mdw.blogspot.kr/p/bbc-microbit.html" target="_blank">http://bluetooth-mdw.blogspot.kr/p/bbc-microbit.html </a>: BT개발자의 블로그
  * <https://m.pxt.io/>
  * <http://www.samsung.com/uk/microbit/>
  * <a href="https://www.techwillsaveus.com/microbit/" target="_blank">https://www.techwillsaveus.com/microbit/</a>
  * <a href="https://www.kitronik.co.uk/bbc-micro-bit-accessories.html" target="_blank">https://www.kitronik.co.uk/bbc-micro-bit-accessories.html</a>
  * <a href="https://codekingdoms.com" target="_blank">https://codekingdoms.com</a>
  * <a href="http://research.microsoft.com/en-us/projects/microbit/" target="_blank">http://research.microsoft.com/en-us/projects/microbit/</a>
  * <a href="https://github.com/Microsoft/microbit-touchdevelop" target="_blank">https://github.com/Microsoft/microbit-touchdevelop</a>