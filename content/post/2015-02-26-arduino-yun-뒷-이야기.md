---
title: Arduino Yún 뒷 이야기
author: openmicrolab
type: post
date: 2015-02-26T02:19:36+00:00
url: /arduino-yun-뒷-이야기/
categories:
  - Wireless
  - Open Source Hardware
tags:
  - wi-fi
  - OSHW
  - Arduino Yun

---
<img loading="lazy" class="alignnone" src="http://arduino.cc/en/uploads/Main/ArduinoYunFront_2.jpg" alt="Arduino Yun" width="1600" height="1067" />

<a href="http://arduino.cc/en/Main/ArduinoBoardYun" target="_blank">Arduino YUN</a>은 Artheros의 AR9331칩셋을 사용하는 모듈을 이용해서 만든 무선랜 보드이다. 물론 이 모듈에는 리눅스가 돌아간다. 전통적으로 무선랜 칩셋업체들은 무선랜 장비를 개발할 만한 업체에게 선별적으로 자신들의 무선랜 레퍼런스 보드의 회로도나 관련 자료들을 NDA를 맺고 공개한다. 이것은 자료를 완전히 오픈했을때 기술지원이 감당이 되지 않아서 이기도 하다. Arduino Yun은 <a href="http://www.doghunter.org/?portfolio=arduino-yun" target="_blank">dog hunter</a>라는 업체로 부터 공급을 받아서 제품화한 것인데 모듈 내부의 회로도는 공개가 되지 않고 인터페이스만 공개가 되어 있다.   <a href="http://arduino.cc/en/uploads/Main/arduino-Yun-schematic.pdf" target="_blank">http://arduino.cc/en/uploads/Main/arduino-Yun-schematic.pdf</a>

Arduino 또는 dog hunter에서 Artheros랑 NDA를 맺고 모든 자료를 받았을 것인데, 오픈할 수 없는 상황이다. 하지만 <a href="http://forum.arduino.cc/index.php?topic=187766.0" target="_blank">Arduino포럼에는 회로도를 오픈하라는 것</a>&#8230;재미있는 것은 처음 이슈를 제기한 사람 [<a href="https://github.com/Squonk42/TL-WR703N" target="_blank">squonk42</a>]이 TL-WR703N을 리버스 엔지니어링 한 사람이라는&#8230; 물론 OSHW의 원칙에 따르면 일부만 오픈해도 상관이 없다. 하지만 그동안의 Arduino의 명성에 좋지않은 이슈라는 것.

참고: <a href="http://hackaday.com/2015/02/24/is-the-arduino-yun-open-hardware/" target="_blank">http://hackaday.com/2015/02/24/is-the-arduino-yun-open-hardware/</a>