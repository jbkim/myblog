---
title: Flash 내장 MCU에서 Flahs가 깨지는 현상 방지
author: openmicrolab
type: post
date: 2011-04-22T06:12:37+00:00
url: /flash-내장-mcu에서-flahs가-깨지는-현상-방지/
dsq_thread_id:
  - "1207050101"
categories:
  - Infomation
  - Development
tags:
  - flash corruption
  - Por
  - power on reset

---
최근의 MCU들은 대부분은 Flash를 내장을 하고 있으며 ISP(In System Programming), IAP(In&nbsp;Application Programming) 기능을 제공을 하고 있다. 간혹 불안한 전원 때문에 내부 Flash가 지워지는 경우가 있는데, 이럴 경우 대책은 다음과 같다.

**해결책**  
간단히 얘기하면 내장된 POR(Power On Reset) 기능을 enable하거나, 외부에 POR칩을 달아주면 되는데, 원리는 MCU가 일정 전압 이하로 내려갈 경우에 리셋을 걸어주어 오동작을 방지하는 것이다.

**POR의 선정**  
외부에 POR&nbsp;칩을 달때 임계전압(Threshold Voltae: Vt) 를 선정을 해야 하는데, 이 임계 전압은 MCU의 동작 가능한 최저 전압 Vmin보다 크고 입력 최저 전압 (Supply Voltage의 최소치)보다 작게 잡으면 된다.

<P style="MARGIN: 0px">
  <img loading="lazy" src="/images/1/cfile22.uf.11278B4D4DB11AB0229FE0.jpg" class="aligncenter" width="497" height="250" alt="" filename="Vt.jpg" filemime="image/jpeg" />
</P>

  
즉&nbsp; **AT89C51RC2를 예**로 들면  
-. Vcc : 2.7V ~ 5.5V  
-. 레귤레이터 출력이 3.235V ~3.365V 라고 가정을 하면,  
&nbsp;&nbsp;&nbsp; POR의 Vt는 2.7V 보다 크고, 3.235V 보다 작은 값을 갖는 부품을 선정하면 된다.

&nbsp; 자세한 내용은 첨부한 내용 참고.

<P style="TEXT-ALIGN: center; MARGIN: 0px">
  <STRONG>External Brown-out Protection for C51 Microcontrollers with Active High Reset Input<br /> </STRONG><a href="/images/1/cfile25.uf.206D42484DB11BB30485D8.pdf" class="aligncenter" filename="doc4183.pdf"  filemime="application/pdf" />cfile25.uf.206D42484DB11BB30485D8.pdf</a>
</P>

  
관련된 특허도 있군요&#8230;.

<DIV style="TEXT-ALIGN: center">
  <STRONG>Method of protecting flash memory from data corruption during fast power down events<br /> </STRONG>
</DIV>

  


<DIV>
  <STRONG><br /> 
  
  <P style="MARGIN: 0px">
    <a href="/images/1/cfile7.uf.207DBA4F4DB11CE216F9BF.pdf" class="aligncenter" filename="US6822899.pdf"  filemime="application/pdf" />cfile7.uf.207DBA4F4DB11CE216F9BF.pdf</a>
  </P></STRONG>
</DIV>