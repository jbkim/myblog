---
title: ARM Cortex M0 – 소개
author: openmicrolab
type: post
date: 2014-01-29T06:12:46+00:00
url: /arm-cortex-m0-소개/
dsq_thread_id:
  - "2193793256"
categories:
  - ARM
tags:
  - arm
  - CortexM0

---
> ARM사는 Acorn Computer Group, Apple 컴퓨터, VLSI Technology의 합작투자회사로 1990년에 Advanced RISC Machine Ltd라는 이름으로 설립

### ARM Cortex-M0의 특징

  * 적은 게이트수: 12,000
  * 저전력 기능 지원 및 높은 에너지 효율성 &#8211; 0.9 DMIPS/MHz
  * 사용하기 쉬운 인터럽트 우선순위 제어를 가진 내장형 인터럽트 콘트롤러
  * Low interrupt latency, 타이밍이 확정적(deterministic)
  * Thumb 지원- 높은 코드 밀도

### ARM 프로세서와 아키텍처

  * 2006년에 Cortex-M3 (ARMv7-M 아키텍쳐) 출시
  * Cortex-M0는 ARMv6-M 아키텍쳐기반
  * ARMv6-M 아키텍쳐는 ARMv7-M의 메모리 맵,  프로그래머 모델과 익셉션 모델, Thumb2 시스템과 ARMv6의 Thumb 명령어 셋 그리고 CoreSight Debug 아키켁쳐를 결합한 형태이며, 여기에 저전력에 특화된 설계로 나온 것이 M0이며, FPRGA 특화된 특성을 넣은 것이 M1이다.

<div id="attachment_2751" style="width: 727px" class="wp-caption aligncenter">
  <a href="/images/2013/12/arm-processor-architecture.jpg"><img aria-describedby="caption-attachment-2751" loading="lazy" class="wp-image-2751 " title="ARM 프로세서 아키텍처의 진화" alt="arm processor architecture" src="/images/2013/12/arm-processor-architecture-1024x483.jpg" width="717" height="338" srcset="/images/2013/12/arm-processor-architecture-1024x483.jpg 1024w, /images/2013/12/arm-processor-architecture-300x141.jpg 300w" sizes="(max-width: 717px) 100vw, 717px" /></a>
  
  <p id="caption-attachment-2751" class="wp-caption-text">
    ARM 프로세서 아키텍처의 진화
  </p>
</div>