---
title: 'Eagel CAD에서 Pick & Place 파일 만들기'
author: openmicrolab
type: post
date: 2016-05-24T07:09:53+00:00
url: /eagel-cad에서-pick-place-파일-만들기/
categories:
  - PCB
tags:
  - Eagle CAD
  - 이글 캐드
  - pick and place

---
Eagle PCB에서 c**entroid-screamingcircuits-smd.ulp**를 실행시킨다. 그러면 csv파일이 생긴다. 이파일은 inch단위의 파일이 생성된다. 만약 mm 단위의 파일이 필요하면 Mountsmd.ulp를 사용한다.

Allegro PCB에서는 **File > Placement&#8230;** 를 실행한다.

참고: <a href="https://www.element14.com/community/community/cadsoft_eagle/blog/2015/01/19/eagle-ulps-every-user-should-know" target="_blank">https://www.element14.com/community/community/cadsoft_eagle/blog/2015/01/19/eagle-ulps-every-user-should-know</a>