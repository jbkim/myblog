---
title: Ultimaker Cura의 구조
author: openmicrolab
type: post
date: 2018-04-18T02:40:59+00:00
url: /ultimaker-cura의-구조/
categories:
  - 3D Printer
tags:
  - Cura
  - Ultimaker Cura
  - curaengine
  - uranium

---
&nbsp;

<img loading="lazy" class="alignnone wp-image-4276" src="https://res.cloudinary.com/openmicrolab/image/upload/v1524019114/Cura_%E1%84%80%E1%85%AE%E1%84%8C%E1%85%A9_d4qxno.png" width="688" height="157" /> 

  * Cura의 대부분은 Python으로 작성되어 있고, 인터페이스는 PyQt를 사용
  * CuraEngine은 슬라이싱을 담당하고, C++로 작성
  * <a href="https://github.com/Ultimaker/Cura" target="_blank" rel="noopener noreferrer">Cura</a>와 <a href="https://github.com/Ultimaker/CuraEngine" target="_blank" rel="noopener noreferrer">CuraEngine</a>(슬라이싱 담당)의 통신에는 Arcus library를 사용.
  * 즉 Cura에서 모델과 슬라이싱 옵션을 CuraEngine에 보내면 G-code를 리턴함
  * <a href="https://github.com/Ultimaker/Uranium" target="_blank" rel="noopener noreferrer">Uranium</a>: 3D 관련 세팅, 3D-scenes을 위한 Python Framework