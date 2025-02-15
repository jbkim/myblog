---
title: Mass Storage bootloader
author: openmicrolab
type: post
date: 2017-12-18T08:01:33+00:00
url: /mass-storage-bootloader/
categories:
  - mbed
  - Microbit
  - Coding
  - Development
tags:
  - USB
  - bootloader
  - Mass Storage bootloader

---
USB device를 가진 MCU를 PC에 연결시 Mass Storage Device로 동작시키고, Hex파일을 copy하면 MCU의 application code가 업데이트 되는 형태.

  * <a href="https://os.mbed.com/handbook/cmsis-dap-interface-firmware" target="_blank" rel="noopener noreferrer">mbed의 CMSIS DAP 인터페이스</a>
  * [NXP사의 자료][1]
  * <a href="http://blog.myelectronics.com.ua/stm32-usb-mass-storage-bootloader/" target="_blank" rel="noopener noreferrer">Russia blogger의 자료</a>
  * [MS의 MakeCode에 적용된 UF2][2]
  * [MSC bootloader (based on UF2) for SAMD21][3]

 [1]: https://www.nxp.com/docs/en/application-note/AN4379.pdf
 [2]: https://github.com/Microsoft/uf2
 [3]: https://github.com/Microsoft/uf2-samd21