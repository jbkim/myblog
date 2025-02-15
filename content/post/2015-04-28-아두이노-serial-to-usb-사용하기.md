---
title: 아두이노 Serial to USB 사용하기
author: openmicrolab
type: post
date: 2015-04-28T06:50:34+00:00
url: /아두이노-serial-to-usb-사용하기/
categories:
  - Arduino
  - Open Source Hardware
  - Development
tags:
  - Arduino
  - 아두이노
  - bootloader
  - serial to USB

---
원본소스는 Mac에서 \Resource\Java\hardware\arduino\firmware\atmegaxxu2 아래에 있다. arduino-usbdfu 또는 arduino-usbserial 를 사용한다. 이 소스에는 USB 프레임워크인 <a href="http://www.fourwalledcubicle.com/LUFA.php" target="_blank">LUFA</a>(Lightweight USB Framework for AVRs)가 빠져있으므로 <a title="LUFA" href="http://www.fourwalledcubicle.com/LUFA.php" target="_blank">http://www.fourwalledcubicle.com/LUFA.php</a> 에서 다운로드한다. 다운로드한 LUFA 폴더를 arduino-usbserial 폴더와 같은 위치에 복사한다.

<p class="p1">
  <span class="s1">make 파일에서 다음과 같은 내용을 수정한다.</span>
</p>

> <p class="p1">
>   <strong>LUFA_PATH</strong>
> </p>
> 
> <p class="p1">
>   <span class="s1"># Path to the LUFA library</span>
> </p>
> 
> <p class="p1">
>   <span class="s1">LUFA_PATH = ../</span>
> </p>
> 
> <p class="p1">
>   <strong>MCU</strong>
> </p>
> 
> <p class="p1">
>   MCU = at90usb162  #atmega16u2와 pin to pin 호환임
> </p>

<p class="p1">
  컴파일된 hex파일은 avr isp등으로 write하면 된다.
</p>

<p class="p1">
  이렇게 작업한 내용은 <a href="https://github.com/jbkim/usbserial" target="_blank">https://github.com/jbkim/usbserial</a>
</p>

<p class="p1">