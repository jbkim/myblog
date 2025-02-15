---
title: 아두이노 스케치를 네트워크로 업로드하기 – Arduino update remotely
author: openmicrolab
type: post
date: 2016-02-05T07:47:54+00:00
url: /아두이노-스케치를-네트워크로-업로드하기-arduino-remote-firmware-update/
categories:
  - Arduino
  - Open Source Hardware
  - Wiznet
tags:
  - 네트워크
  - Arduino
  - 아두이노
  - remote
  - firmware
  - update

---
아두이노 보드의 펌웨어는 USB 케이블을 PC와 연결후 PC상에서 잡히는 것은 COM 포트를 통해 아두이노 IDE를 통해 업데이트가 된다. 좀 더 구체적으로는 <a href="http://www.nongnu.org/avrdude/" target="_blank">avrdude</a>라는 프로그램을 써서 <a href="http://www.atmel.com/images/doc2591.pdf" target="_blank">stk500프로토콜</a>을 사용해서 프로그램이 된다.

### 아두이노 스케치를 네트워크로 업로드하기

**필요한 것들**

  * <a href="http://www.wiznet.co.kr/product-item/wiz550s2e/" target="_blank">Wiznet의 WIZ550S2E</a> &#8211;  1개
  * Arduino pro mini &#8211; 테스트에 사용한 아두이노 보드
  * 와이어링 케이블 &#8211; WIZ550S2E와 Arduino pro mini를 연결
  * TFTP server program &#8211; Windows의 경우 <a href="http://tftpd32.jounin.net/tftpd32_download.html" target="_blank">tftpd</a>, 맥의 경우 <a href="http://ww2.unime.it/flr/tftpserver/" target="_blank">Tftp Server</a>
  * 아두이노 IDE 프로그램

#### 케이블 연결 및 설정

WIZ550S2E는 Serial to Ethernet 게이트웨이 모듈로 시리얼로 들어온 데이터는 네트워크로 보내고, 네트워크에서 들어온 데이터는 시리얼로 보낸다. <a href="http://wizwiki.net/wiki/doku.php?id=products:wiz550s2e:wiz550s2eds_kr" target="_blank">WIZ550S2E의 회로도</a>를 보면 J1에 있는 입력핀들은 풀업이 되어 있어서, 아두이노와 연결에 필요한 핀은  3V3D, GND, TXD, RXD, STATUS2 핀이다.

[<img loading="lazy" class="size-medium wp-image-3532 aligncenter" src="/images/2016/02/wiz550s2e_pin-300x253.jpg" alt="wiz550s2e_pin" width="300" height="253" srcset="/images/2016/02/wiz550s2e_pin-300x253.jpg 300w, /images/2016/02/wiz550s2e_pin.jpg 611w" sizes="(max-width: 300px) 100vw, 300px" />][1]

TXD, RXD는 아두이노의 RXD, TXD에 연결을 하고 STATUS2를 아두이노의 DTR에 연결을 한다. 이 DTR 신호는 아두이노 보드의 리셋에 연결이 되어 있다.  따라서 아두이노 IDE에서 스케치 업로드를 하면 연결된 보드의 DTR을 트리거링해서 아두이노 보드를 리셋시키고, 아두이노는 bootloader로 진입한다. 그리고 이 bootloader에서는 일정 시간안에 stk500 프로토콜에 해당되는 메시지가 들어오면 펌웨어를 업데이트하고, 그렇지 않으면 0번지에 위치한 프로그램으로 jump한다. 이 DTR을 트리거링 하는 것은 WIZ550S2E 펌웨어를 수정해서 적용을 할 것이다.

**모듈의 설정**

모듈의 설정은 Configtool을 사용해서 설정을 하며, 아래 그림을 참고한다. 특별한 것은 없고 IP, Port, Working mode 정도만 설정하면 되고, **<span style="text-decoration: underline;">주의 할 것은 baud rate인데 Arduino pro mini의 경우는 57600</span>**이다. 각 보드를 프로그래밍하는 baudrate는 맥의 경우 Arduino.app/Contents/Java/hardware/arduino/avr/boards.txt파일에 정의가 되어 있다.

[<img loading="lazy" class="aligncenter wp-image-3535 size-full" src="/images/2016/02/configtool.png" alt="configtool" width="972" height="822" srcset="/images/2016/02/configtool.png 972w, /images/2016/02/configtool-300x254.png 300w" sizes="(max-width: 972px) 100vw, 972px" />][2]

#### WIZ550S2E 펌웨어 수정하기

WIZ550S2E 모듈의 하드웨어 자료와 펌웨어 소스, Configtool의 코드까지 모든 소스는 <a href="http://wizwiki.net/wiki/doku.php?id=products:wiz550s2e:wiz550s2e_download" target="_blank">위키</a>에 있다. Configtool은 모듈설정에 필요하니 다운로드를 해서 설치를 하고, 수정할 펌웨어는 <a href="https://github.com/Wiznet/WIZ550S2E" target="_blank">github</a>에서 다운로드를 한다. 그리고 소스를 컴파일할 컴파일러는 NXP의 <a href="https://www.lpcware.com/lpcxpresso" target="_blank">LPCXPresso</a>는 회원가입 후 다운로드해서 설치를 한다. 참고로 위키에는 LPCXpresso v7.5.0\_254에 최적화되어 있다고 하는데 최근 버전인 8.0도 전혀 문제가 없다. github에서 다운로드한 zip파일을 LPCXpresso에서 import해서 WIZ550S2E\_APP의 S2E.c를 수정하는데, 수정한 코드는 단 한줄로 TCP 연결이 이루어졌을때 LED를 켜는 부분을 켰다가 끄는 형태로 수정을 한다. 그럼 STATUS2의 핀이 Low에서 High로 되어 DTR를 토글시켜 아두이노가 리셋이 된다.

[<img loading="lazy" class="aligncenter size-large wp-image-3536" src="/images/2016/02/lpcecpress-1024x761.png" alt="lpcecpress" width="1024" height="761" srcset="/images/2016/02/lpcecpress-1024x761.png 1024w, /images/2016/02/lpcecpress-300x223.png 300w, /images/2016/02/lpcecpress.png 1394w" sizes="(max-width: 1024px) 100vw, 1024px" />][3]

#### 수정된 펌웨어 업로드하기

펌웨어 업데이트는 TFTP를 사용하므로 설치한 TFTP 서버에서 bin파일을 모듈이 수신 할 수 있도록 설정을 한다. Confitool로 search를 해서 업에디트 할 모듈을 찾은 후 F/W Uploading 버튼을 누르고, 서버 IP를 PC의 IP주소, Port를 69, File Name을 WIZ550S2E_App.bin로 하고 OK 버튼을 누르면 모듈은 재부팅 후 TFTP로 펌웨어를 업데이트 한다. 참고로 펌웨어를 수정하면서 기존 펌웨어와 구별을 하기 위해 common.h에서 모듈의 펌웨어를 9.0.0으로 바꾸었다.  한줄 수정된 펌웨어의 코드는 <a href="https://github.com/jbkim/WIZ550S2E/releases/tag/v9.0.0" target="_blank">github</a>에서&#8230; 바이너리는 <a href="https://www.dropbox.com/s/yr1fcah08uj8ujg/WIZ550S2E_App.bin?dl=0" target="_blank">dropbox</a>에서 다운로드.

**Avrdude 설정 변경**[  
][4] 스케치를 업로드 할때는 연결된 시리얼로 데이터는 전송하는데, avrdude의 설정을 강제로 변경을 해서 아두이노 IDE가 서버의 IP:Port로 접속을 하게한다.

맥의 경우 아두이노가 설치된 폴더/Contents/Java/hardware/arduino/avr/platform.txt에 있는 내용중

> tools.avrdude.upload.pattern=&#8221;{cmd.path}&#8221; &#8220;-C{config.path}&#8221; {upload.verbose} -p{build.mcu} -c{upload.protocol} -P{serial.port} -b{upload.speed} -D &#8220;-Uflash:w:{build.path}/{build.project_name}.hex:i&#8221;

**-P{serial.port}를 -P net:host:port**로 변경한다. 즉 host:port를 모듈의 IP와 port로 수정한다.

**동작테스트**

아래그림과 같이 연결을 하고 전원을 연결한다. 그리고 아두이노 IDE에서 스케치를 업로드를 하면 컴파일이 되고 avrdude는 모듈의 IP로 접속을 해서 아두이노를 프로그래밍한다. 간단하게 blink예제를 타이밍을 바꿔서 테스트를 해봤는데 잘된다. 나중에 시간이 되면 Avrdude 설정을 바꾸지 않고, Arduino IDE에서 IP:Port를 입력할 수 있게 코드를 수정해서 빌드하면 좋을 듯~~

<img loading="lazy" class="aligncenter wp-image-3539" src="/images/2016/02/wiz550s2e_arduino-1024x768.jpg" alt="wiz550s2e_arduino" width="612" height="459" srcset="/images/2016/02/wiz550s2e_arduino-1024x768.jpg 1024w, /images/2016/02/wiz550s2e_arduino-300x225.jpg 300w" sizes="(max-width: 612px) 100vw, 612px" /> 

&nbsp;

업데이트 &#8211; Mac에서 작업을 해서 Windows에서도 될 줄 알았는데, avrdude 코드를 보니 다음과 같이 win32에서는 network을 지원을 하지 않는다. 즉 net:<host>:<port> 형태는 바로 &#8220;ser_open(): network connects are currently not implemented for Win32 environments&#8221; 라는 메시지를 뿌리고 리턴한다.

> /*  
> * If the port is of the form &#8220;net:<host>:<port>&#8221;, then  
> * handle it as a TCP connection to a terminal server.  
> *  
> * This is curently not implemented for Win32.  
> */  
> if (strncmp(port, &#8220;net:&#8221;, strlen(&#8220;net:&#8221;)) == 0) {  
> fprintf(stderr,  
> &#8220;%s: ser_open(): network connects are currently not&#8221;  
> &#8220;implemented for Win32 environments\n&#8221;,  
> progname);  
> return -1;  
> }

 [1]: /images/2016/02/wiz550s2e_pin.jpg
 [2]: /images/2016/02/configtool.png
 [3]: /images/2016/02/lpcecpress.png
 [4]: /images/2016/02/wiz550s2e_arduino.jpg