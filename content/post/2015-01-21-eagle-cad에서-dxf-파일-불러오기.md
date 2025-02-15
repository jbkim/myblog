---
title: Eagle CAD에서 DXF 파일 불러오기
author: openmicrolab
type: post
date: 2015-01-21T07:08:41+00:00
url: /eagle-cad에서-dxf-파일-불러오기/
categories:
  - Infomation
  - Development
tags:
  - Eagle CAD
  - dxf
  - ulp
  - 보드의 원점 바꾸기

---
### DXF파일 불러오기

Eagle CAD에서 보드의 외곽을 그릴 때 20 Dimension 레이어에서 Width 0으로 외곽선을 그린다. 일반적으로 보드가 사각형이면 그리는데 어려움은 없는데, 보드에 곡선이 있으면 쉽지 않다. 기구 설계하는 쪽에서 보드 외곽을 만들어 논 것이 있으면 이것을  DXF 파일로 변환하고, 이것을 Eagle CAD에서 불러와서 그대로 사용이 가능한다. Eagle CAD에서 바로 이 기능을 지원하는 것은 아니고 import-dxf 라는 ulp를 받아서 사용하면 된다.  이 파일은 <a href="http://www.cadsoftusa.com/downloads/ulps" target="_blank">http://www.cadsoftusa.com/downloads/ulps</a> 에서 import-dxf를 검색하면 import-dxf-1_6.ulp를 받을 수 있다.

ulp를 실행한 후 dxf파일을 선택하고 Metric, Scale을 설정하면 된다. 단 DXF파일은 도면 형태가 아니고, 보드의 외곽만 있어야 제대로 import가 된다.

<img loading="lazy" class="alignnone" src="http://openmicrolab.cdn2.cafe24.com/import_dxf.png" alt="" width="546" height="567" /> 

### 보드의 원점 바꾸기

Import한 보드의 외곽이 원점(origin)에 위치하게 하는 방법은 보드의 외곽을 전체 선택하고 마우스로 옮길 수도 있지만 이 방법 보다는 다음의 명령어를 사용하는 것이 한번에 정확하게 된다. 여기서 dX dY는 옮길 위치의 좌표

> move (>0 0) (dX dY)