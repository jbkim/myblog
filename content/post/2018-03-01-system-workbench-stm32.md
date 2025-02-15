---
title: System Workbench for STM32
author: openmicrolab
type: post
date: 2018-03-01T09:04:19+00:00
url: /system-workbench-stm32/
categories:
  - ARM
  - IoT
  - Development
  - Tool
tags:
  - STM32
  - 이클립스
  - System Workbench for STM32

---
System Workbench for STM32를 설치하는 방법은 2가지이다. 인스톨 프로그램으로 설치하는 방법과 기존에 설치되어 있는 이클립스에 설치하는 방법이 있다.

### **인스톨 프로그램**

  * System Workbench for STM32를 <a href="http://www.openstm32.org/Downloading%2Bthe%2BSystem%2BWorkbench%2Bfor%2BSTM32%2Binstaller" target="_blank" rel="noopener noreferrer">링크</a>에서 다운로드 한다.
  * 다운로드 받은 바이너리 파일의  퍼미션을 수정후 파일을 실행한다.

> chmod 755 install\_sw4stm32.run then ./install\_sw4stm32.run

<img loading="lazy" class="alignnone wp-image-4222" src="https://res.cloudinary.com/openmicrolab/image/upload/v1519891095/System_Workbench_for_STM32_wlfr7n.png" width="568" height="431" /> 

문제는 이렇게 설치를 하다가 다음과 같은 에러메시지가 나오고 더 이상 진행이 되지 않는다.

<img loading="lazy" class="alignnone wp-image-4224" src="https://res.cloudinary.com/openmicrolab/image/upload/v1519892823/error_nqiihq.png" width="765" height="132" /> 

### **이클립스에서 추가하는 방법**

  * 이클립스에서“Help >> Install New Software”를 선택
  * http://ac6-tools.com/Eclipse-updates/org.openstm32.system-workbench.update-site-v2를 입력하고, 이름은 System Workbench for STM32 &#8211; Bare Machine edition으로 한다.

<img loading="lazy" class="alignnone wp-image-4230" src="/images/2021/03/install_bo1tqe-1.png" width="633" height="511" /> 

  * 인스톨 전에 다음과 같이 맥의 게이트키퍼를 disable후 설치를 하고, 설치후 enable한다.

> #To disable  
> sudo spctl &#8211;master-disable  
> #To enable  
> sudo spctl &#8211;master-enable

### 시작하기

  * File -> New -> Project&#8230; -> C/C++ -> C Project
  * 프로젝트 이름을 정하고, 프로젝트 타입은 AC6 STM32 MCU project를 선택한다.

<img loading="lazy" class="alignnone wp-image-4229" src="/images/2021/03/setup_z2cjh1.png" width="497" height="548" /> 

  * 다음 스텝에서 프로그래밍을 할 보드를 선택한다.
  *  StdPeriph 또는 Cube Hal을 사용할 수 있다.

### 기타

  * [Creating a new project][1]{.link}
  * [Creating a custom board][2]{.link}
  * [Configuring build settings][3]{.link}
  * [Creating debug configuration][4]{.link}
  * [Debugging a project][5]{.link}
  * [Importing an mbed program][6]{.link}
  * [Importing a STCubeMX generated project][7]{.link}
  * [Using CCM Memory][8]{.link}

### 참고

  * <a href="http://www.openstm32.org/HomePage" target="_blank" rel="noopener noreferrer">http://www.openstm32.org/HomePage</a>
  * <a href="http://www.openstm32.org/Getting%2Bstarted%2Bwith%2BSystem%2BWorkbench%2Bfor%2BSTM32" target="_blank" rel="noopener noreferrer">Getting started with System Workbench for STM32</a>
  * <a href="http://www.openstm32.org/Supported%2BSTM32%2Bboards" target="_blank" rel="noopener noreferrer">지원하는 보드의 종류</a>

 [1]: http://www.openstm32.org/Creating%2Ba%2Bnew%2Bproject ""
 [2]: http://www.openstm32.org/Creating%2Ba%2Bcustom%2Bboard ""
 [3]: http://www.openstm32.org/Configuring%2Bbuild%2Bsettings ""
 [4]: http://www.openstm32.org/Creating%2Bdebug%2Bconfiguration ""
 [5]: http://www.openstm32.org/Debugging%2Ba%2Bproject ""
 [6]: http://www.openstm32.org/Importing%2Ban%2Bmbed%2Bprogram ""
 [7]: http://www.openstm32.org/Importing%2Ba%2BSTCubeMX%2Bgenerated%2Bproject ""
 [8]: http://www.openstm32.org/Using%2BCCM%2BMemory ""