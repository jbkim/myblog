---
title: ARM Cortex M0 – 기술적 개요
author: openmicrolab
type: post
date: 2014-02-06T10:40:05+00:00
url: /arm-cortex-m0-기술적-개요/
dsq_thread_id:
  - "2278483067"
categories:
  - ARM
tags:
  - arm
  - Cortex M0

---
### 일반적인 정보

  * 폰노이만 아키텍처(단일버스 인터페이스)를 가지는 32비트 RISC 프로세서
  * ARMv6 아키텍쳐 : M0, M1(FPGA에 최적화)이 ARMv6 아키텍쳐이며, M3는 ARMv7 아키텍처임. 상위호환이 가능해 M0코드가 M3로 쉽게 이식이 가능.
  * 56개의 명령어: Thumb 명령어 지원, Thumb-2 명령어의 일부 지원

<p style="text-align: center;">
  <a href="/images/2014/01/Cortex-M0-block-diagram.png"><img loading="lazy" class="size-full wp-image-2759 aligncenter" alt="Cortex-M0 block diagram" src="/images/2014/01/Cortex-M0-block-diagram.png" width="340" height="307" srcset="/images/2014/01/Cortex-M0-block-diagram.png 340w, /images/2014/01/Cortex-M0-block-diagram-300x270.png 300w" sizes="(max-width: 340px) 100vw, 340px" /></a>
</p>

### ARM Cortex-M0의 특징

  * 0.9DMIPS/MHz
  * 프로세스 코어는 3단계 파이프라인
  * NVIC: 프로그램 가능한  4개의 서로 다른 우선 순위 레벨을 가질 수 있으며, 32개까지의 interrrupt request를 받을 수 있다.
  * WIC (Wakeup Interrupt Controller)는 옵션
  * OS지원을 위한 System Tick지원

### ARM Cortex-M0의 장점

  * 에너지 효율성 &#8211; 슬립모드와 연계되어 있다. 즉 평소에는 슬립모드에 있다가 인터럽트가 발생을 하면 빨리 처리하고 다시 슬립모드로 들어감.
  * 8, 16비트의 제약을 극복 &#8211; 32비트 linear address 사용(더 큰 메모리의 사용 가능), 더 큰 스텍사용(참고로 8051은 256바이트), 향상된 명령어 셋으로 더 작은 크기의 코드 가능( 참고로 8051은 항상 ACC를 사용해야 함)

### 저전력을 가능하게 하는 요소들

  * 적은 게이트수 : 최소 설정으로는 12K, 일반적으로 17~25K
  * 높은 효율성 : 0.9 DMIPS/MHz (80486DX가 0.81 DMIPS/MHz 였다는&#8230;)
  * 슬립모드 : WIC(Wakeup Interrupt Controller), 2 개의 슬립모드: WFI(Wait for Interrupt ), WFE(Wait for Event)
  * 로직셀 향상 : Ultra Low Leakage 로직 셀 라이브러리 도입

<p style="text-align: center;">
  <a href="/images/2014/01/average-current.png"><img loading="lazy" class=" wp-image-2762 aligncenter" alt="average current" src="/images/2014/01/average-current.png" width="671" height="241" srcset="/images/2014/01/average-current.png 959w, /images/2014/01/average-current-300x107.png 300w" sizes="(max-width: 671px) 100vw, 671px" /></a>
</p>

> 즉 물리적으로 누설전류가 적은 로직셀, 최적화된 게이트 수를 통해 성능이 좋은 칩으로 슬립모드를 제공하므로 저전력이 가능하다.

관련자료 다운로드 [wpdm_file id=10]