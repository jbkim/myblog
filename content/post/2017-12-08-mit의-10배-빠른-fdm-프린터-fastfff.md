---
title: 'MIT의 10배 빠른 FDM 프린터 –  FastFFF'
author: openmicrolab
type: post
date: 2017-12-08T08:21:23+00:00
url: /mit의-10배-빠른-fdm-프린터-fastfff/
categories:
  - 3D Printer
tags:
  - 3d printer
  - MIT
  - 10배 빠른 FDM 프린터
  - FastFFF
  - FDM

---
### FDM 프린터에서 속도를 높이기 위해 기존에 사용한 방법

<ul id="yui_3_17_2_1_1512714297221_422">
  <li>
    노즐 사이즈를 크게해서 필라멘트를 단위시간당 많이 출력하게 함. 해상도 문제
  </li>
  <li>
    펠릿 방식으로 기존 필라멘트 보다 더 잘 밀어내게 함
  </li>
  <li>
    히팅 구간을 더 크게해서 필라멘트에 열이 잘 전달되게 함
  </li>
  <li>
    높은 성능의 프린터 보드를 사용해서 기구부의 움직임을 빠르게 함
  </li>
</ul>

<img loading="lazy" class="alignnone wp-image-4156" src="/images/2021/03/mit_fastFFF_chjrxq.jpg" width="343" height="336" /> 

### MIT가 적용한 방식

  * 힘을 더 잘 주기 위해 나사산이 있는 필라멘트 사용. 기존 방식은 pinch wheel방식이며 이것은 nut feed 방식임
  * 2 단계 히팅 &#8211; 기존 히트 블럭 + 레이저(50W near-infrared laser pre-heats). 단 필라멘트 색에 따라 레이저를 조정해야 함
  * 서보 모터를 사용

<img loading="lazy" class="alignnone wp-image-4157" src="/images/2021/03/buildrate_x2jgij.jpg" width="524" height="297" /> 

### 이슈

  * 나사산이 있는 필라멘트가 필요
  * FastFFF 방식의 특허
  * 더 빠른 프린터와 속도 비교를 한 것이 아니고 일반적인 프린터와 속도를 비교함
  * 이정도 속도가 빨라지면 실제적인 이득은 무엇인가?

### 참고

  * <a href="http://www.fabbaloo.com/blog/2017/11/30/mits-laser-powered-3d-printer-is-this-the-speed-weve-been-waiting-for" target="_blank" rel="noopener noreferrer">http://www.fabbaloo.com/blog/2017/11/30/mits-laser-powered-3d-printer-is-this-the-speed-weve-been-waiting-for</a>
  * <a href="http://www.ni.com/white-paper/3656/ko/" target="_blank" rel="noopener noreferrer">스테핑 모터와 서보 모터</a>
  * <a href="http://openmicrolab.com/download/fastfff/" target="_blank" rel="noopener noreferrer">저널에 실린 내용</a>