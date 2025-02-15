---
title: Allegro PCB에서 DXF파일 만드는 법
author: openmicrolab
type: post
date: 2015-03-24T11:12:08+00:00
url: /allegro-pcb에서-dxf파일-만드는-법/
categories:
  - Infomation
  - Development
  - Tool
tags:
  - dxf
  - Allegro PCB

---
Allegro PCB에서 DXF파일 만드는 법은 다음과 같다.

  1. 보드파일 brd를 연다.
  2. File > Export -> Select dxf를 선택
  3. Layer Conversion File에서 임의의 이름을 지정한다. ex) name.cnv
  4. Dxf output 파일에는 변환할 파일의 이름
  5. Layer Conversion File에서 Edit 을 클릭하고 dxf로 변환하기를 원하는 항목만 체크한다.
  6. **중요한 것은 아래 그림과 같이 새로운 DXF Layer를 만들고 DXF layer에 이것을 지정한다.**

<img loading="lazy" class="alignnone" src="http://openmicrolab.cdn2.cafe24.com/allegro_dxf.png" alt="" width="1350" height="735" />