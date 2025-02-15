---
title: Eagle CAD tip
author: openmicrolab
type: post
date: 2016-05-20T05:49:51+00:00
url: /eagle-cad-tip/
categories:
  - Tip
tags:
  - Eagle CAD

---
**1. Commnad Line 활용**

<div class="table-responsive">
  <table class="table table-bordered" summary="Schematic Editor ">
    <caption><strong>Schematic Editor</strong></caption> <tr>
      <td>
        <strong>Tool Name</strong>
      </td>
      
      <td>
        <strong>Command</strong>
      </td>
    </tr>
    
    <tr>
      <td>
        Add element
      </td>
      
      <td>
        a,ad,add
      </td>
    </tr>
    
    <tr>
      <td>
        Net
      </td>
      
      <td>
        ne,Net
      </td>
    </tr>
    
    <tr>
      <td>
        Move
      </td>
      
      <td>
        Mov,move
      </td>
    </tr>
    
    <tr>
      <td>
        Copy
      </td>
      
      <td>
        Cop,copy
      </td>
    </tr>
    
    <tr>
      <td>
        Name
      </td>
      
      <td>
        n,na,nam,name
      </td>
    </tr>
    
    <tr>
      <td>
        Value
      </td>
      
      <td>
        v,va,value
      </td>
    </tr>
    
    <tr>
      <td>
        Label
      </td>
      
      <td>
        l,la,lab,labe,label
      </td>
    </tr>
    
    <tr>
      <td>
        Text
      </td>
      
      <td>
        T,tex,text
      </td>
    </tr>
  </table>
</div>

<div class="table-responsive">
  <table class="table table-bordered" summary="Board Editor ">
    <caption><strong>Board Editor</strong></caption> <tr>
      <td>
        <strong>Tool Name </strong>
      </td>
      
      <td>
        <strong>Command </strong>
      </td>
    </tr>
    
    <tr>
      <td>
        Route
      </td>
      
      <td>
        rou,rout,route
      </td>
    </tr>
    
    <tr>
      <td>
        Ripup
      </td>
      
      <td>
        ri,rip,ripu,ripup
      </td>
    </tr>
    
    <tr>
      <td>
        Via
      </td>
      
      <td>
        Vi,via
      </td>
    </tr>
    
    <tr>
      <td>
        Ratsnest
      </td>
      
      <td>
        r,ra,rat,rasts,ratsn,ratsne,ratsnest
      </td>
    </tr>
  </table>
</div>

**2. Show 명령어: ex) Show R***

**라우팅시 오른쪽 마우스 클릭 &#8211; 와이어 꺽이는 스타일 변경**

<img loading="lazy" class="alignnone" src="http://www.allaboutcircuits.com/uploads/articles/changelayerbend.gif" width="620" height="350" /> 

**3. 라우팅시 가운데 스크롤 휠 클릭 &#8211; 레이어변경**

<img loading="lazy" class="alignnone" src="http://www.allaboutcircuits.com/uploads/articles/change_layer_m.png" width="626" height="352" /> 

**4. Ratsnest시 좌측 하단에 라우팅 되지 않은 정보 확인**

<img loading="lazy" class="alignnone" src="http://www.allaboutcircuits.com/uploads/articles/ratsnestnum.jpg" width="341" height="93" /> 

**5. 부품 라이브러리**

  * <a href="https://github.com/sparkfun/SparkFun-Eagle-Libraries" target="_blank">SparkFun</a>
  * <a href="https://github.com/adafruit/Adafruit-Eagle-Library" target="_blank">AdaFruit</a>
  * <a href="http://dangerousprototypes.com/docs/Dangerous_Prototypes_Cadsoft_Eagle_parts_library" target="_blank">Dangerous Prototypes</a>
  * <a href="http://www.element14.com/community/community/cadsoft_eagle/eagle_cad_libraries" target="_blank">Element14 Eagle Cad Lib Search</a>
  * <a href="http://www.cadsoftusa.com/downloads/libraries" target="_blank">CADSoft Lib Search</a>

**6. 라이브러리를 만들때 이글에서 만든 Ref-packages.lib 참고**

**7. Ratsnest로 깔린 카파를 모두 없앨때 &#8211;  <span style="color: #ff0000;">ripup @ ;</span>**

**8. 라우팅을 airwire 말고 중간에서 할때 &#8211; CTRL을 누르고 라우팅을 한다.**

**참고:**

  * <a href="http://www.allaboutcircuits.com/technical-articles/eagle-cad-tips-and-tricks/" target="_blank">http://www.allaboutcircuits.com/technical-articles/eagle-cad-tips-and-tricks/</a>
  * <a href="http://www.allaboutcircuits.com/technical-articles/eagle-cad-tips-and-tricks-part-2/" target="_blank">http://www.allaboutcircuits.com/technical-articles/eagle-cad-tips-and-tricks-part-2/</a>