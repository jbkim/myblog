---
title: mbed – SeeedArch 프로그래밍하기
author: openmicrolab
type: post
date: 2014-03-06T06:42:53+00:00
url: /mbed-seeedarch-프로그래밍하기/
dsq_thread_id:
  - "2371401938"
categories:
  - ARM
  - mbed
tags:
  - Arduino
  - arm
  - mbed
  - SeeedArch
  - Automator

---
### SeeedArch

<a href="http://mbed.org/" target="_blank">mbed</a>의 플랫폼 중의 하나인 Seeedstudio에서 만든 보드, <a href="http://mbed.org/platforms/Seeeduino-Arch/" target="_blank">SeeedArch</a>를 테스트중이다. 이 보드의 스펙은 다음과 같다.

  * mbed enabled 
      * online development tools
      * easy to use C/C++ SDK
      * lots of published libraries, projects
  * Standard Arduino Appearance, two Grove connectors 
      * available with 3.3V compatible shields
      * a large number of grove modules
  * Drag-n-drop programming
  * NXP LPC11U24 MCU 
      * Low power ARM Cortex-M0 Core
      * 48MHz, 32KB Flash, 8KB RAM, 4KB EEPROM
      * USB Device, 2xSPI, UART, I2C

이 보드의 가장 큰 특징은 보드의 형태가 아두이노 보드와 같아서 아두이노 쉴드를 연결할 수 있다.

[<img loading="lazy" class="alignnone  wp-image-2900" alt="800px-Arch_Pinout.jpg" src="/images/2014/03/800px-Arch_Pinout.jpg.png" width="560" height="455" srcset="/images/2014/03/800px-Arch_Pinout.jpg.png 800w, /images/2014/03/800px-Arch_Pinout.jpg-300x243.png 300w" sizes="(max-width: 560px) 100vw, 560px" />][1]

코딩은 mbed의 웹컴파일러로 하고 다운로드 역시 msd로 잡히는 외장드라이브에 copy를 하면 되는데, Mac이나 Linux에서는 Windows와 달리 drag & drop이 안된다.

### 프로그래밍 방법 (Mac)

  * 보드의 왼쪽에 있는 리셋 버튼을 길게 누른다. (짧게 누르면 H/W 리셋이고, 길게 누르면 ISP 모드이다.)
  * 그러면 Finder에 CRP DISABLED 라고 스토리지가 잡힌다. Windows에서는 이 폴더에 있는 firmware.bin을 지우고 새로운 firmware.bin을 copy하면 되지만 Mac에서는 Terminal에서 다음과 같이 dd 명령어로 copy한다.
  * **dd if=새로운 firmware 파일명 of=/Volumes/CRP\ DISABLD/firmware.bin conv=notrunc**

좀 더 쉽게하기위해서 Mac의 Automator를 사용하여 쉘 스크립트를 만든다.

  * **dd if=$* of=/Volumes/CRP\ DISABLD/firmware.bin conv=notrunc**

[<img loading="lazy" class="alignnone  wp-image-2901" alt="Automator_SeeedArch" src="/images/2014/03/Automator_SeeedArch-1024x821.png" width="614" height="493" srcset="/images/2014/03/Automator_SeeedArch-1024x821.png 1024w, /images/2014/03/Automator_SeeedArch-300x240.png 300w, /images/2014/03/Automator_SeeedArch.png 1072w" sizes="(max-width: 614px) 100vw, 614px" />][2]

### LED blink 프로그래밍

[<img loading="lazy" class="alignnone  wp-image-2902" alt="SeeedArch" src="/images/2014/03/SeeedArch-674x1024.jpg" width="404" height="614" srcset="/images/2014/03/SeeedArch-674x1024.jpg 674w, /images/2014/03/SeeedArch-197x300.jpg 197w, /images/2014/03/SeeedArch.jpg 1534w" sizes="(max-width: 404px) 100vw, 404px" />][3]

관련정보: <a href="http://www.seeedstudio.com/wiki/Seeeduino_Arch" target="_blank">SeeedStudio WiKi</a>

 [1]: /images/2014/03/800px-Arch_Pinout.jpg.png
 [2]: /images/2014/03/Automator_SeeedArch.png
 [3]: /images/2014/03/SeeedArch.jpg