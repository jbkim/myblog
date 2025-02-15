---
title: Freescale FRDM-K82F 보드
author: openmicrolab
type: post
date: 2016-04-19T08:03:31+00:00
url: /freescale-frdm-k82f-보드/
categories:
  - ARM
  - IoT
tags:
  - Freescale
  - 이클립스
  - FRDM-K82F

---
<img loading="lazy" class="alignnone wp-image-3639" src="http://res.cloudinary.com/openmicrolab/image/upload/a_0/v1461052393/Freescale_FRDM-K82F_aaxwqd.jpg" alt="" width="314" height="314" />

### Freescale FRDM-K82F 보드의 개발 환경설정

  * <a href="https://nxp.flexnetoperations.com/control/frse/download?agree=Accept&element=6912747" target="_blank">Kinetis SDK 다운로드 및 설치</a>
  * <a href="http://www.nxp.com/webapp/swlicensing/sso/downloadSoftware.sp?catid=KINETIS-KDS-IDE" target="_blank">Kinetis Design Studio (KDS) 다운로드 및 설치</a>
  * <a href="http://developer.mbed.org/media/downloads/drivers/mbedWinSerial_16466.exe" target="_blank">윈도우즈의 경우 virtual COM port 드라이버 설치</a>

### 1. 이클립스 업데이트 파일 설치

“Help”->Check for Updates를 누르고, Processor Expert for Kinetis만 선택하고 업데이트 한다.

&#8220;Help&#8221; -> &#8220;Install New Software&#8221;를 선택하고 Add 버튼 > Archive 버튼을 눌러서 SDK 설치 폴더 아래 /tools/eclipse\_update 폴더에서 KSDK\_<version>\_Eclipse\_Update_zip file. 를 선택한다

### 2. 플랫폼 라이브러리 빌드하기

<img loading="lazy" class="alignnone wp-image-3640" src="http://res.cloudinary.com/openmicrolab/image/upload/v1461052909/lib_kykbku.png" alt="" width="272" height="399" /> 

&#8220;File->Import&#8221;를 선택후 &#8220;General&#8221;을 눌러서 &#8220;Existing Projects into Workspace&#8221;를 선택한다.  
루트 디렉토리는 <install\_dir>/lib/ksdk\_platform_lib/kds/K82F25615 를 선택하고 finish를 클릭한다.  
메뉴에 헤머 아이콘을 눌러 빌드한다.

### 3. 데모 프로그램을 빌드하기

<install\_dir>/examples/frdmk82f/demo\_apps/<demo_name>/kds 아래있는 데모 프로그램을 플랫폼 라이브러리 빌드 할때와 마찬가지로 빌드한다.

예를 들면 hello\_world의 경우 <install\_dir>/examples/frdmk82f/demo\_apps/hello\_world/kds  
메뉴에 헤머 아이콘을 눌러 빌드한다.

### 4. 데모 프로그램을 다운로드 및 디버깅

FRDM-K82F는 기본적으로 mbed/CMSIS-DAP debug interface 가 설치가 되어있으므로 KDS에서 다운로드 디버깅을 하기위해서는 J-Link OpenSDAv2.1를 설치해야 한다. 리셋 버튼을 누른상태에서 “SDA USB” USB 포트를 연결해서 전원을 연결한다. 그러면 BOOTLOADER로 폴더가 잡힌다.  
<a href="https://www.segger.com/opensda.html" target="_blank">https://www.segger.com/opensda.html</a> 여기에서 OpenSDA V2.1: Download JLink\_OpenSDA\_V2\_1\_2015-10-13.zip 을 다운로드후 압축을 풀고 bin파일을 BOOTLOADER 폴더에 넣으면 다시 JLINK라는 폴더로 잡힌다.

Run > Debug Configurations에서 맨 아래있는 GDB SEGGER J-Link를 선택하고 디버깅을 한다.  
Hellow World의 경우 시리얼 터미널 설정은 115200. 보드의 전원 및 디버깅을 위해서 USB SDA 포트와 PC를 연결한다.

<a href="http://www.nxp.com/products/software-and-tools/run-time-software/kinetis-software-and-tools/ides-for-kinetis-mcus/freescale-freedom-development-platform-for-kinetis-k82-k81-and-k80-mcus:FRDM-K82F?tab=In-Depth_Tab&tid=van/frdm-k82f/startnow#PlugItIn" target="_blank">관련 튜토리얼 페이지</a>