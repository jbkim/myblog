---
title: 3D Printer – S3G, X3G 파일 포맷
author: openmicrolab
type: post
date: 2017-05-29T03:59:13+00:00
url: /3d-printer-s3g-x3g-파일-포멧/
categories:
  - 3D Printer
tags:
  - 3d printer
  - X3G
  - 메이커봇
  - S3G
  - Maketbot

---
  * S3G는 &#8220;Sanguino3 Gcode&#8221;의 약자로 3D 프린터를 제어하기 위한 언어
  * 자세한 내용은 <a href="https://github.com/makerbot/s3g/blob/master/doc/s3gProtocol.md" target="_blank" rel="noopener noreferrer">이 링크</a>를 참고
  * Makerbot과 Sailfish 팀에서 기능을 추가해서 S3G와 구별하기 위해 X3G를 만듦
  * Makerbot 프린터는 gcode를 직접받아서 출력하지 않음
  * 따라서 ReplicatorG, MakerBot MakerWare, MakerBot Desktop 프로그램의 슬라이서에서 Gcode를 변환하는 기능이 있음
  * OctoPrint의 경우 <a href="https://github.com/markwal/OctoPrint-GPX/blob/master/README.md" target="_blank" rel="noopener noreferrer">다음 링크</a> 참고

참고: <a href="http://www.sailfishfirmware.com/doc/details-s3g-and-x3g.html#x52-1340009.3" target="_blank" rel="noopener noreferrer">http://www.sailfishfirmware.com/doc/details-s3g-and-x3g.html#x52-1340009.3</a>