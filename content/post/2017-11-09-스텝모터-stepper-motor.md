---
title: 스텝모터 – Stepper Motor
author: openmicrolab
type: post
date: 2017-11-09T05:10:43+00:00
url: /스텝모터-stepper-motor/
categories:
  - 3D Printer
tags:
  - 3d printer
  - A4988
  - 스텝모터
  - Stepper Motor
  - TMC2130

---
#### 스텝모터

스텝 모터는 일반적으로 스텝 사이즈 규격 (예 : 1.8 ° 또는 200 회전당)을 가진다. 즉 360도, 한바퀴 회전시 2000 스텝이 필요하니, 한 스텝당 1.8 °가 움직인다.

#### 마이트로 스텝핑

스텝모터 드라이버의 기능중 마이트로 스텝핑기능은 이 스텝을 분주를 해서 더 정밀하게 모터를 회전시킨다. 예를 들면 <a href="https://www.pololu.com/file/download/a4988_DMOS_microstepping_driver_with_translator.pdf?file_id=0J450" target="_blank" rel="noopener noreferrer">A4988 드라이버</a>의 경우 다음과 같이 1/16까지 가능하니, 한 스텝당 0.1125 °(1.8 °/16)까지 제어가 가능하다. 반면 <a href="https://www.trinamic.com/fileadmin/assets/Products/ICs_Documents/TMC2130_datasheet.pdf" target="_blank" rel="noopener noreferrer">TMC2130드라이버</a>의 경우 1/256까지 가능하므로 1스텝당 0.007°(1.8°/256)까지 가능하다.

<img loading="lazy" class="alignnone wp-image-4095" src="/images/2021/03/TMC21xxx_axvwen-1.png" width="913" height="920" /> 

#### 참고

  * <a href="https://github.com/watterott/SilentStepStick" target="_blank" rel="noopener noreferrer">github 자료</a>
  * [hackaday 기사][1]
  * <a href="http://reprap.org/wiki/StepStick" target="_blank" rel="noopener noreferrer">Reprap 위키자료</a>

 [1]: https://hackaday.com/2016/09/30/3d-printering-trinamic-tmc2130-stepper-motor-drivers-shifting-the-gears/