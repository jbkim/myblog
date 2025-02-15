---
title: NXP LPC 시리즈 맥에서 개발 환경 – Flash Magic
author: openmicrolab
type: post
date: 2014-05-23T07:29:47+00:00
url: /nxp-lpc-시리즈-맥에서-개발-환경-flash-magic/
dsq_thread_id:
  - "2706966269"
categories:
  - ARM
  - Development
  - Tool
tags:
  - NXP
  - LPC
  - 맥
  - Flash Magic

---
NXP의 LPC 시리즈는 이클립스 기반의 툴인 <a href="http://www.lpcware.com/lpcxpresso/home" target="_blank">LPCExpresso</a>를 제공한다. 대부분의 개발 환경은 <a href="http://openmicrolab.com/lpc810-arm-cortexm0-project-1/" target="_blank">지난 포스팅</a>을 참고. 따라서 Mac에서도 윈도우즈와 동일한 개발환경을 구축할 수 있다.  LPC 시리즈 칩 역시 시리얼 부트로더가 내장이 되어 있어서 쉽게 flash를 write할 수 있으며, <a href="http://www.flashmagictool.com/" target="_blank">FlashMagic</a>이라는 툴을 사용한다. 원래 윈도우 기반으로 개발된 툴을 Mac에 Wine을 사용하여 포팅이 되어 있다. 그래서 시리얼 포트도 COM1, COM2 이런 식으로 표시가 된다.  
![FlashMagic][1] 

Mac에서 잡힌 시리얼 포트를 FlashMagic이 구동이 될때 COM1, COM2.. 으로 매핑이 되는데, 이것을 확인해서 해당되는 COM 포트를 넣어주면 된다. 매핑된 포트를 찾는 방법은 다음의 그림을 참고&#8230; 대개 serial to USB 컨버터를 사용하는데, Mac에서는 cu.\*의 형태와 tty.\*의 형태가 잡히는데, **cu.*의 형태로 잡힌 포트를 사용하면 된다.**  
![FlashMagic 포트찾기][2]  
즉 명령어는

> ls -l /Applications/FlashMagic.app/Contents/Resources/dosdevices

그런데 문제는 추가적으로 연결되는 Seirial to USB 케이블들을 찾아주지를 못한다. 따라서 이때는 기존에 저장된 정보를 지우고 스크립트를 다시 실행해서 정보를 업데이트 해야 한다.

> rm ./FlashMagic.app/Contents/Resources/dosdevices/COM*  
> ./FlashMagic.app/Contents/Resources/WineskinStartupScript  
> ls -l ./FlashMagic.app/Contents/Resources/dosdevices

관련정보: <a href="http://forum.flashmagictool.com/index.php?topic=4130.0" target="_blank">http://forum.flashmagictool.com/index.php?topic=4130.0</a>

 [1]: http://openmicrolab.cdn2.cafe24.com/FlashMagic_program.png
 [2]: http://openmicrolab.cdn2.cafe24.com/FlashMagic.png