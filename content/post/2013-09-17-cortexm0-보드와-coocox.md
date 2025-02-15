---
title: CortexM0 보드와 CooCox
author: openmicrolab
type: post
date: 2013-09-17T07:30:08+00:00
url: /cortexm0-보드와-coocox/
dsq_thread_id:
  - "1783128754"
categories:
  - ARM
  - Infomation
tags:
  - CortexM0
  - CooCox
  - Nuvoton

---
### NXP LPC1114 보드

이전 블로그를 보니 2011년도 초에 NXP와 Nuvoton의 Cortex M0에 대해 쓴 <a href="http://openmicrolab.com/nuvoton%EC%9D%98-cortex-m0-%EC%B9%A9/" target="_blank">블로그 포스팅</a>이 있었는데 최근 당시에 CooCox로 부터 받은 보드와 최근에 Nuvoton에서 받은 보드를 테스트를 해봤다. 아래 그림에서 위에 있는 것은 NXP칩을 사용한 <a href="http://sg.element14.com/embest/colinkex-lpc11c14-evb/board-eval-lpc1114-w-colinkex/dp/2136555" target="_blank">LPC1114보드</a>이고, 아래 그림은 Nuvoton의 <a href="http://www.nuvoton.com/hq/enu/ProductAndSales/ProductLines/MicrocontrollerApplicationIC/ARMMicrocontroller/ARMCortexTMM0/Documents/NuTiny-SDK-M051%20user%20manual%20EN%20V1.0.pdf" target="_blank">M0516NBL</a> 을 사용한 보드이다.

[<img loading="lazy" class="alignnone  wp-image-2683" alt="CortexM0 보드" src="/images/2013/09/CortexM0-보드-1024x625.jpg" width="717" height="438" srcset="/images/2013/09/CortexM0-보드-1024x625.jpg 1024w, /images/2013/09/CortexM0-보드-300x183.jpg 300w, /images/2013/09/CortexM0-보드.jpg 1825w" sizes="(max-width: 717px) 100vw, 717px" />][1]

최근 이런 개발 보드들의 특징은 디버거를 포함을 하고 있는데, 보드의 좌측 부분이 디버거 기능을 하며,  <a href="http://openmicrolab.com/cmsis-dap-%EB%9E%80/" target="_blank">CMSIS-DAP</a> 기능을 한다.

하지만 몇 년 지난 보드를 다시 PC에 연결을 해보니 일단 연결 부터가 되지 않는다. 아마도 이 보드의 CooCoox의 ColinkEX가 업데이트가 됐는가 싶어서 이 보드의 ColinkEX f/w를 확인해 보니 예상한 대로 f/w가 업데이트 되어 있다. 관련 자료: <a href="http://www.coocox.org/CoLinkGuide/CoLinkDIY.htm" target="_blank">http://www.coocox.org/CoLinkGuide/CoLinkDIY.htm</a>

  * JP1을 쇼트시키고 USB 전원을 연결하면 LPC1343 칩의 내부 메모리가 &#8220;&#8221;CRP2 ENABLD&#8221; or &#8220;CRP DISABLD&#8221;의 레이블을 가진 MSD로 잡힌다.
  * 여기에 파일을 제거하고 위 링크에서 <a href="http://www.coocox.com/Tools/ColinkEx_firmware_V0.4.bin" target="_blank">F/W</a>를 다운로그해서 카피한다.
  * JP1을 오픈하고 USB 전원을 다시 연결한다.

물론 PC에는 <a href="http://www.coocox.org/Colinkex.htm" target="_blank">드라이버</a>를 설치를 해야한다.

### Nuvoton NuTiny-M051보드

이 보드의 왼쪽 부분의 디버거의 이름은 Nulink이며, 보드를 PC에 연결을 하니 USB-HID로 잡힌다. NXP 보드와 마찬가지로 디버거를 이용해 개발을 하고 양산시에는 보드를 잘라서 F/W를 구울수 있는 구조로 되어 있다. 사용해 보니 mbed에 있는 CMSIS-DAP와 다른 점은 호스트에 연결되는 USB로 시리얼까지 처리를 하지는 않아서 시리얼 출력을 보려면 보드에서 선을 따로 뽑아야 한다. 하지만 NXP 보드는 보드에 RS232C 드라이버 칩과 소켓이 있어서 바로 연결을 할 수 있다.

### CooCox 개발 환경

CooCox 역시 당시 <a href="http://openmicrolab.com/coocox/" target="_blank">블로그 포스팅</a>에도 소개를 했었는데 최근 다시 설치를 해서 확인을 해보니 다양한 Cortex 칩들을 지원을 하고 있고, 커뮤니티도 제법 커져있다. 하지만 당시와 달라진 점은 ARM GCC 를 따로 설치를 해주고 경로를 설정을 해줘야 한다.

  * <a href="https://launchpad.net/gcc-arm-embedded/+download" target="_blank">https://launchpad.net/gcc-arm-embedded/+download</a>

위 사이트에서 gcc를 다운로드 받고 설치를 한후, Project >> Select Toolchain Path를 지정을 한다.

[<img loading="lazy" class="alignnone size-full wp-image-2685" alt="CoIDE_Set_1" src="/images/2013/09/CoIDE_Set_1.jpg" width="652" height="467" srcset="/images/2013/09/CoIDE_Set_1.jpg 652w, /images/2013/09/CoIDE_Set_1-300x214.jpg 300w" sizes="(max-width: 652px) 100vw, 652px" />][2]

### Blink 테스트

입베디드 보드에서의 Hello World와 같은 LED 깜박이기 예제를 돌려보자. 프로젝트를 만드는 것은 쉽다.

[<img loading="lazy" class="alignnone  wp-image-2687" alt="coocox" src="/images/2013/09/coocox-1024x769.png" width="819" height="615" srcset="/images/2013/09/coocox-1024x769.png 1024w, /images/2013/09/coocox-300x225.png 300w, /images/2013/09/coocox.png 1285w" sizes="(max-width: 819px) 100vw, 819px" />][3]

  * Project >> New Project : 프로젝트 이름을 정한다.
  * 칩 또는 보드를 선택을 하는데, 만약 이 툴에서 제공하는 보드리스트에 사용하는 보드가 있다면 보드를 선택을 하고, 없다면 칩을 선택한다.
  * 사용할 컴포넌트를 선택한다.  만약 GPIO를 선택을 하면  CMSIS Core와 CMSIS Boot는 자동으로 로드 된다. (스텝 3)
  * 좌측 창의 Component 부분의 GPIO에  2개의 예제가 있다고 표시가 된다. 이것을 선택을 하고 Blink예제를 add하면 프로젝트의 main 함수에서 blink 함수를 호출을 한다.
  * Blink.c 파일을 보면 Port2의 GPIO9 를 on/off 하는데, 내가 가지고 있는 보드의 설정과 동일하다. 즉 코드를 수정할 필요가 없다.
  * Project  >> Build (단축키 F7)를 한후, Flash >> Program Download를 선택한다. (보드의 JP2는 쇼트)
  * 보드의 JP2를 오픈하고 리셋 버튼을 누르면 다운로드 한 코드가 동작을 한다.

이상으로 코드 한줄 코딩하지 않고 개발 환경 설정하고 칩에 F/W까지 다운로드해서 동작을 확인했다. 사용을 해보니 참 편한데 한가지 아쉬운 점은 CooCox가 Windows만 지원을 한다는 것. LPCXpresso의 경우는 3가지 OS (Win, MAC, Linux)를 다 지원하는데&#8230;.

 [1]: /images/2013/09/CortexM0-보드.jpg
 [2]: /images/2013/09/CoIDE_Set_1.jpg
 [3]: /images/2013/09/coocox.png