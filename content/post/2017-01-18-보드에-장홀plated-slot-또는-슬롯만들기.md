---
title: 보드에 장홀(plated slot) 또는 슬롯만들기
author: openmicrolab
type: post
date: 2017-01-18T05:53:46+00:00
url: /보드에-장홀plated-slot-또는-슬롯만들기/
categories:
  - PCB
tags:
  - Eagle CAD
  - 이글 캐드
  - 장홀
  - plated slot
  - slot

---
**Routing 과 Milling의 차이**

> “Routing” describes the cutting of the board profile, outline or contour.  We use a 2 mm cutter for this.  Any feature which can be cut with the 2 mm cutter is part of the profile.  
> “Milling” refers to any slots or cut-outs inside the PCB, but also to any slots in the profile of the PCB which can’t be cut with a 2 mm cutter.

즉 라우팅은 2mm 커터로 보드의 외곽을 자르는 것이고, 밀링은 보드 안쪽에 있는 cut-out 또는 슬롯을 더 작은 툴로 작업을 하는 것이다.

**보드에 슬롯을 만드는 법**  
일반적이지 않기 때문에 PCB 업체에서 작업을 빠트릴 수 있다. 따라서 따로 알려주고, 0.50 mm 라인으로 작업을 하는데 Eagle CAD에서는 Eagle CAD에서는 Milling Layer 46에 작업을 한다.  
하지만 PCB 업체에 따라서 이 작업이 안될 수 도 있다.

**참고**  
<a href="http://docs.oshpark.com/submitting-orders/cutouts-and-slots/" target="_blank" rel="noopener noreferrer">http://docs.oshpark.com/submitting-orders/cutouts-and-slots/</a>  
<a href="http://www.eurocircuits.com/blog/158-Slots-and-cut-outs" target="_blank" rel="noopener noreferrer">http://www.eurocircuits.com/blog/158-Slots-and-cut-outs</a>

**이글캐드에서 장홀(plated slot) 만들기**

<img loading="lazy" class="alignnone wp-image-3853" src="http://res.cloudinary.com/openmicrolab/image/upload/v1484718729/NbXRR_lbvx6n.png" width="540" height="418" /> 

드릴을 중첩적으로 배치하면 돼지만 DRC에서 에러가 난다. <a href="http://dangerousprototypes.com/docs/Crude_way_of_making_plated_slots_in_Eagle#Plated_slot_using_holes" target="_blank" rel="noopener noreferrer">관련 자료</a>

방법은 위의 슬롯만들기와 동일하게 Milling 레이어에서 작업을 하고, 업체에 얘기를 해야 한다. ㅠㅠ

**참고**  
<a href="http://electronics.stackexchange.com/questions/198590/how-to-add-holes-in-package-and-create-elongated-plated-holes-eagle" target="_blank" rel="noopener noreferrer">http://electronics.stackexchange.com/questions/198590/how-to-add-holes-in-package-and-create-elongated-plated-holes-eagle</a>  
<a href="http://electronics.stackexchange.com/questions/202551/eagle-oval-pad" target="_blank" rel="noopener noreferrer">http://electronics.stackexchange.com/questions/202551/eagle-oval-pad</a>

https://www.autodesk.com/products/eagle/blog/what-you-didnt-know-about-eagle-slotted-holes/