---
title: CAM350에서 Eagle CAD NC drill 데이터를 제대로 불러오기
author: openmicrolab
type: post
date: 2015-04-24T09:54:17+00:00
url: /cam350에서-eagle-cad-nc-drill-데이터를-제대로-불러오기/
categories:
  - Open Source Hardware
  - Infomation
  - Development
tags:
  - Eagle CAD
  - CAM350
  - gerber
  - PCB Panelization

---
<img loading="lazy" class="alignnone" src="http://openmicrolab.cdn2.cafe24.com/cam350_merge.png" alt="" width="326" height="367" />

위 그림은 CAM350에서 Eagle CAD로 만든 거버데이터를 Auto import로 불러온 것이다. drill data의 좌표가 맞지 않아서 우측 상단에 표시된 것 을 볼 수 있다. 이렇게 된 이유는 Eagle CAD에서 NC 데이터를 출력하는 포맷은 2.5인데 CAM350의 기본 설정은 2.4이다. 따라서 다음과 같이 CAM350의 Auto import 포맷에서 Digits항목을 2, 5로 수정하면 된다.

<img loading="lazy" class="alignnone" src="http://openmicrolab.cdn2.cafe24.com/cam350_drill_setting.png" alt="" width="475" height="304" /> 

단순히 거버 데이터를 보는 수준이면 상관이 없는데 샘플 PCB가격을 아끼기 위해 <a href="http://openmicrolab.com/cam350%EC%9C%BC%EB%A1%9C-2%EA%B0%9C%EC%9D%98-%EA%B1%B0%EB%B2%84%EB%A5%BC-%ED%95%98%EB%82%98%EB%A1%9C-%ED%95%A9%EC%B9%98%EA%B8%B0/" target="_blank">2개 이상의 거버데이터를 합기기</a>(영어로 PCB Penalization)위해서는 중요한 이슈이다.