---
title: IAR 컴파일러에서 J-LINK 사용하기 2 – EWARM5.41
author: openmicrolab
type: post
date: 2011-02-18T02:32:21+00:00
url: /iar-컴파일러에서-j-link-사용하기-2-ewarm541/
dsq_thread_id:
  - "1164887499"
categories:
  - Development
  - Tool
tags:
  - iar
  - J-LINK
  - EWARM5.41
  - 디버깅

---
이전 포스트 &#8220;<A title="[http://liketheocean.tistory.com/62]로 이동합니다." href="http://liketheocean.tistory.com/62" target=_blank>IAR 컴파일러에서 J-LINK 사용하기</A>&#8221; 는 EWARM4.xx 버전에서 동작하는 것이였습니다.  
컴파일러 버젼을 5.41로 바꿨는데, 이전 버젼에서 사용하던 메뉴들이 없어졌네요.  
이전 버젼과 호환성을 유지를 해줘야 하는데&#8230; -_-;;  
J-link와 연결은 되는데, &#8220;Programming flash memory&#8221; 창이 떠서 멈줘있는 현상이 있어서 다시 확인을 하니 몇가지 주의해야 할 설정이 있습니다.  
컴파일러 옵션 설정에서  


  


<UL style="LIST-STYLE-TYPE: disc">
  <br /> 
  
  <LI style="LINE-HEIGHT: 1.2">
    Output Converter => intel extended
  </LI>
  <br /> 
  
  <LI style="LINE-HEIGHT: 1.2">
    Linker/ Config&nbsp;=> icf 파일 을 제대로 설정
  </LI>
  <br /> 
  
  <LI style="LINE-HEIGHT: 1.2">
    Debugger / Download => board 파일을 제대로 설정</p> <p>
      </LI></UL>
    </p>