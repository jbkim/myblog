---
title: NXP MCUXpresso 사용법
author: openmicrolab
type: post
date: 2018-08-10T04:10:27+00:00
url: /nxp-mcuxpresso-사용법/
categories:
  - ARM
  - Development
tags:
  - NXP
  - NXP MCUXpresso 사용법
  - MCUXpresso

---
MCU 벤더들에서 제공하는 무료툴들은 대부분 이클립스 기반의 툴을 수정해서 제공을 한다. 그래서 하나의 툴에 익숙하면 다른 툴도 쉽게 쓸 수 있지만 다른 기능들은 메뉴얼을 보면서 익혀야 한다. NXP사의 MCUXpresso도 약간 특이한 점이 있어서 정리.

**1. 먼저 회원가입을 하고, <a href="https://mcuxpresso.nxp.com/en/dashboard" target="_blank" rel="noopener noreferrer">https://mcuxpresso.nxp.com/en/dashboard</a> 에서 보드나 칩을 선택해서 설정을 한후 SDK파일을 다운로드 받는다.**

<img loading="lazy" class="alignnone wp-image-4376" src="https://res.cloudinary.com/openmicrolab/image/upload/v1533873657/mcuxpresso_0_qtna5m.png" width="732" height="667" /> 

**2. MCUXpress에서 Installed SDKs에 이 파일을 Drag & Drop한 후 좌측의 Import SDK examples를 클릭한다.**

<img loading="lazy" class="alignnone wp-image-4375" src="https://res.cloudinary.com/openmicrolab/image/upload/v1533873657/mcuxpresso_1_damxra.png" width="774" height="578" /> 

**3. 보드, 칩을 선택하고 Next 버튼을 클릭**

<img loading="lazy" class="alignnone wp-image-4377" src="https://res.cloudinary.com/openmicrolab/image/upload/v1533873657/mcuxpresso_2_dlf3s8.png" width="671" height="563" /> 

**4. 원하는 예제를 선택하면 관련 코드가 import된다.**

<img loading="lazy" class="alignnone wp-image-4378" src="https://res.cloudinary.com/openmicrolab/image/upload/v1533873656/mcuxpresso_3_rhy2ey.png" width="667" height="559" /> 

참고로 MCUXPresso Config Tools도 내장이 되어 있어서 pin, clock설정이 가능하다.

<img loading="lazy" class="alignnone wp-image-4379" src="https://res.cloudinary.com/openmicrolab/image/upload/v1533873657/mcuxpresso_4_tgqbca.png" width="961" height="619" /><img loading="lazy" class="alignnone wp-image-4380" src="https://res.cloudinary.com/openmicrolab/image/upload/v1533873657/mcuxpresso_5_hfklfg.png" width="972" height="626" /> 

관련 메뉴얼 &#8211; <a href="https://www.nxp.com/docs/en/user-guide/MCUXSDKGSUG.pdf" target="_blank" rel="noopener noreferrer">Getting Started with MCUXpresso SDK</a>