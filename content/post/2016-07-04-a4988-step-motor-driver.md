---
title: A4988 Step motor driver
author: openmicrolab
type: post
date: 2016-07-04T09:05:28+00:00
url: /a4988-step-motor-driver/
categories:
  - 3D Printer
tags:
  - 3D 프린터
  - A4988

---
3D프린터에 많이 사용되는 스텝모터 드라이버인 Allegro사의 A4988칩. 모터드라이버에서 가장 중요한 것은 전류인데, 이것을 설정하는 방법은 칩의 17번 핀 REF에 걸리는 전압에 의해 결정이 된다.

> _Current Limit = VREF × 2.5_

**즉 만약 Vref가 0.3이면 Current limit는 0.75A. 그런데 full step mode일때의 전류는 Current limit의 70%로 제한이 되므로 만약 1A의 전류제한으로 설정을 하려면 1/0.7 = 1.4A로 가정을 하고 계산을 한다. 따라서 Vref = 1.4 / 2.5 = 0.56V 가 되게 설정을 한다.**

<img loading="lazy" class="alignnone wp-image-3695" src="http://res.cloudinary.com/openmicrolab/image/upload/v1467622936/A4988_qphbse.png" width="447" height="501" /> 

또한가지 모터에 흐르는 전류를 결정짓는 것은 SENSE1, SENSE2에 연결된 Rs 저항이다. 데이터 시트에 보면 공식은 다음과 같다.

> I = Vref / (8 x Rs)