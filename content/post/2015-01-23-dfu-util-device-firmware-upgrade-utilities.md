---
title: Dfu-util – Device Firmware Upgrade Utilities
author: openmicrolab
type: post
date: 2015-01-23T06:18:02+00:00
url: /dfu-util-device-firmware-upgrade-utilities/
categories:
  - Development
  - Tool

---
USB 인터페이스를 가지는 디바이스의 firmware를 업데이트 하는 툴

### Supported Devices

  * [Openmoko Neo1973][1]
  * [Openmoko Freerunner][2]
  * [Leaflabs Maple][3]
  * [OpenPCD and OpenPICC][4]
  * [Qi Hardware ATUSB][5] (use dfu-util 0.7)
  * [Osmocom SIMtrace][6]
  * Many devices using the [DfuSe DFU extension][7] from ST, for instance: 
      * [DSO nano][8]
      * [Spark Core][9]
      * STM32F2/F3/F4 built-in bootloader
      * Some STR750-based devices, e.g. USB2CAN

맥에서는 Homebrew를 사용해서 다음과 같이 설치한다.

> &#8220;brew install dfu-util&#8221;

참고: <a href="http://dfu-util.sourceforge.net/" target="_blank">http://dfu-util.sourceforge.net/</a>

 [1]: http://wiki.openmoko.org/wiki/Neo_1973
 [2]: http://wiki.openmoko.org/wiki/Neo_FreeRunner
 [3]: http://leaflabs.com/Maple
 [4]: http://www.openpcd.org/
 [5]: http://downloads.qi-hardware.com/people/werner/wpan/web/
 [6]: http://bb.osmocom.org/trac/wiki/SIMtrace
 [7]: http://dfu-util.sourceforge.net/dfuse.html
 [8]: http://www.seeedstudio.com/depot/micro-digital-storage-oscilloscopedso-nano-p-512.html
 [9]: https://www.spark.io/