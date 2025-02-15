---
title: ARM Cortex M0 – 아키텍처
author: openmicrolab
type: post
date: 2014-02-06T09:40:43+00:00
url: /arm-cortex-m0-아키텍처/
dsq_thread_id:
  - "2333982812"
categories:
  - ARM
tags:
  - arm
  - Cortex M0
  - 아키텍처

---
### Programmer&#8217;s Model

<p style="text-align: center;">
  <a href="/images/2014/02/CortexM0-Processor-mode.png"><img loading="lazy" class="wp-image-2828 aligncenter" alt="CortexM0 Processor mode" src="/images/2014/02/CortexM0-Processor-mode-1024x476.png" width="614" height="286" srcset="/images/2014/02/CortexM0-Processor-mode-1024x476.png 1024w, /images/2014/02/CortexM0-Processor-mode-300x139.png 300w, /images/2014/02/CortexM0-Processor-mode.png 1227w" sizes="(max-width: 614px) 100vw, 614px" /></a>
</p>

> ARMv6-M 아키텍처에서는 쓰레드 모드와 핸들러 모드가 거의 같다. 유일한 차이는 쓰레드 모드에서는 CONTROL이라는 특별 레지스터의 설정으로 shadow된 스텍포인터를 사용한다는 것이다.

### 레지스터

<p style="font-size: 14px;">
  <img loading="lazy" style="font-size: 13px;" alt="201402061550.jpg" src="/images/2014/02/201402061550.jpg" width="561" height="368" />
</p>

> 로드 스토어 아키텍쳐: 메모리에 있는 데이터를 처리하기 위해 이 데이터는 메모리로 부터 레지스터 뱅크의 레지스터에 옮겨져서 내부 프로세서에 의해 처리되고, 이것이 다시 메모리에 쓰여진다.  
> Cortex-M0는 13개의 32비트 범용 레지스터와 몇개의 특별(special)레지스터를 가진다.

#### R0-R12

범용 레지스터이며, 대부분의 16비트 Thumb 명령어들은 R0-R7, 하위(Low)레지스터만 액세스 가능하다. 이 레지스터들은 리셋시에 초기값이 정해져 있지 않다.

#### R13, SP (스텍 포인터)

2개의 스텍포인터가 존재하며, Push, Pop은 32비트 명령이기 때문에 스텍포인터는 항상 32비트의 최하위 2 비트는 항상 0이다.

-. MSP (SP_main) : 메인 스텍 포인터 &#8211; 리셋시에 사용되는 기본 설정 스텍포인터이며, 익셉션 핸들러가 실행될 때도 사용이 됨, 초기값은 스타트업 동작시 벡터테이블에서 처음 32비트 워드를 가져온다.  
-. PSP (SP_process) : 프로세스 스텍 포인터 &#8211; 쓰레드 모드(익셉션을 처리하지 않을 때)에서만 사용됨, 초기값이 정해지지 않음.

#### R14, LR (링크 레지스터)

함수 호출 또는 서브루틴의 복귀주소를 저장하기 위해 사용이 된다.

#### R15, PC (프로그램 카운터)

읽기시에는 파이프라인설계 특성 때문에 현재 명령어 주소 + 4값이 읽혀진다.

#### PSR, 프로그램 상태 레지스터

이 레지스터는 다음 3개의 레지스터들로 구성이 된다.

-. Application PSR (APSR) : 조건 분기를 위해 N(음수), Z(제로), C(캐리 또는 바로우), V(오버플로우)  
-. Interrupt PSR (IPSR) : 현재 실행중인 ISR(인터럽트 서비스 루틴)의 번호를 표시한다.  
-. Execution PSR (EPSR) : Cortex-M0에서 T비트는 항상 1 (Thumb 상태를 표시), 만약 이 비트가 0이면 Hard Fault 익셉션이 발생한 것이다.

<img loading="lazy" alt="201402061613.jpg" src="/images/2014/02/201402061613.jpg" width="544" height="143" /> 

이 세개의 레지스터는 xPSR 라 불리는 하나의 레지스터를 통해 액세스 된다.

#### PRIMASK: 인터럽트 마스크 특별 레지스터

<img loading="lazy" alt="201402061621.jpg" src="/images/2014/02/201402061621.jpg" width="480" height="72" /> 

PRIMASK를 설정하면 NMI나 Hard Fault 익셉션을 제외한 모든 인터럽트를 차단한다.

#### CONTROL: 특별레지스터

<img loading="lazy" alt="201402061622.jpg" src="/images/2014/02/201402061622.jpg" width="480" height="90" /> 

> 리셋이 된 후(Active stack pointer = 0)에는 MSP가 사용이되지만 , 쓰레드 모드에서 Active stack pointer가 1로 되면 PSP가 선택이 된다. 간단한 응용에서는 MSP만 사용이 되지만 OS가 사용이 될 경우 PSP가 사용이 되는 데 이것은 빠른 Context switching을 위한 것이다. MSP의 초기값은 프로그램 메모리의 시작 부분에 저장이 되지만 PSP의 초기값은 정해지지 않으며, 사용하기전에 프로그램에 의해 초기화가 되야 한다.

### 메모리 시스템의 개요

<img loading="lazy" alt="201402061628.jpg" src="/images/2014/02/201402061628.jpg" width="240" height="480" /> 

### 스텍 메모리 동작

  * First-in, Last-out 동작 메카니즘
  * Push &#8211; 스텍에 메모리를 저장, 스텍 포인터의 주소는 감소한다.
  * Pop &#8211; 메모리에 저장된 데이터를 복구, 스텍 포인터의 주소는 증가한다.
  * Cortex-M0의 경우 full descending 스텍 모델 &#8211; 이것은 스텍 포인터가 항상 스텍 메모리의 마지막에 저장된 데이터를 가리킨다는 의미인다.
  * Push를 했는데 Pop을 하지 않을 경우 스텍 오버플로우 발생

### 익셉션과 인터럽트

<img loading="lazy" alt="201402061654.jpg" src="/images/2014/02/201402061654.jpg" width="480" height="261" />  
<img loading="lazy" alt="Vector table" src="/images/2014/02/201402061655.jpg" width="358" height="480" /> 

### NVIC

  * Flexible 인터럽트 관리: s/w로 인터럽트를 enable / disable 가능, Pending 상태를 set / clear가능
  * 중첩된 인터럽트 지원 &#8211; 선점형(preemption)
  * 벡터 방식의 익셉션 진입
  * 인터럽트 마스팅

### 디버그 시스템

Halt mode debug, stepping, register access를 제공하고, BPU(Breakpoint Unit), DWT(Data Watch point)같은 디버그 기능을 제공한다.JTAG 연결(nTRST, TCK, TDI, TMS, TDP등 5핀 사용)과 Serial-Wire 연결(Serial Write Clock, Serial Write Data등 2핀 사용)은 동일한 컨넥터를 사용이 가능하다. 즉 TCK와 Serial Write Clock이 공유되고, TMS와 Serial Write Data핀이 공유되며 나머지는 NC이다.

### Startup Sequence

<img loading="lazy" alt="IMG_0003" src="/images/2014/02/IMG_0003.jpg" width="480" height="383" /> 

> 프로세서가 리셋이 되면 다음과 같은 순서로 동작을 한다.
> 
> 1. 0x00000000 번지에 저장이 되어 있는 MSP의 초기값을 읽는다. MSP의 초기값 = 스텍의 시작 번지
> 
> 2. 0x00000004 번지에 저장이 되어 있는 리셋 벡터를 읽는다.
> 
> 3. 리셋 벡터에 저장된 번지의 명령어를 패치한다.
> 
> 만약 부트코드가 0x000000C0 번지부터 시작을 하면, Thumb 코드임을 나타내기 위하여 최하위 비트를 1로 설정한 값이 리셋 벡터에 저장이 되어 있어야 한다.