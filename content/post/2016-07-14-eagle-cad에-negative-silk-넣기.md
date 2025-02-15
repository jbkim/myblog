---
title: Eagle CAD에 네거티브 실크 넣기
author: openmicrolab
type: post
date: 2016-07-14T08:02:23+00:00
url: /eagle-cad에-negative-silk-넣기/
categories:
  - PCB
tags:
  - Eagle CAD
  - 네거티브 실크
  - negative silk

---
아두이노 보드의 모델명 같은 것은 일반 실크가 아닌 네거티브 실크로 되어 있다. Eagle Cad에서 이 작업을 하려면 negasilk.ulp를 사용하면 되는데 방법은 다음과 같다.

  * 실크를 TXT로 적은 후 41 tRestrict 레이어에 만들고 넣을 위치를 잡는다.
  * 41레이어를 끄고 나머지 레이어만 켜서 블럭으로 잡아서 다른 위치로 이동한다.
  * 41레이어를 켜서 Top에서 폴리곤으로 글자를 둘러싸고 Copper pour를 한다. 다른 위치로 이동한 회로에는 Copper pour가 되지 않도록 폴리곤 작업을 하지 않는 것이 좋다.
  * negasilk.ulp를 실행하면 작업 폴더에 스크립트(확장자 scr)가 생긴다.
  * 이 스크립트를 열어서 3번째 라인에 LAYER 21;을 입력한다. 즉 21번째 레이어에 네거티브 실크를 생성할 것이다.
  * 네거티브 실크가 생성된 위치의 Top에 깔린 Copper 및 글씨를 지운다.
  * 이동한 회로들을 다시 원점으로 이동한후 폴리곤 작업을 하고 Copper pour를 한다.

<https://www.youtube.com/watch?v=lVpzqZfN2A4>

이외에 PCB를 예쁘게 만들기 위해 BMP 이미지를 불러올 수도 있고, DXF를 불어와서 작업을 할 수도 있다. 이것을 위해서는 <a href="https://todbot.com/blog/2011/06/06/from-illustrator-to-eagle-vector-graphics-in-circuits/" target="_blank">https://todbot.com/blog/2011/06/06/from-illustrator-to-eagle-vector-graphics-in-circuits/</a>를 참고.

&nbsp;