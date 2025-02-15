---
title: 이클립스(Eclipse)에서 아두이노(Arduino)사용하기
author: openmicrolab
type: post
date: 2014-08-12T03:08:15+00:00
url: /이클립스eclipse에서-아두이노arduino사용하기/
dsq_thread_id:
  - "2920254363"
categories:
  - Arduino
  - Open Source Hardware
  - Development
  - Tool
tags:
  - Arduino
  - 아두이노
  - 이클립스
  - Eclipse
  - 아두이노 이클립스
  - Arduino Eclipse plugin

---
### 이클립스 개발환경에서 아두이노사용하기

  1. 이클립스(Eclipse) 설치 <a href="http://www.eclipse.org/downloads/" target="_blank">http://www.eclipse.org/downloads/</a> **Eclipse IDE for C/C++ Developers** 를 설치
  2. 아두이노 이클립스 플러그인:  <a href="http://www.baeyens.it/eclipse/" target="_blank">저작자의 홈페이지</a> &#8211; <a href="http://www.baeyens.it/eclipse/installAdvice.shtml" target="_blank">Installation advice</a>, 가 있으니 참고. 플러그인 설치는 이클립스를 실행후 **Help >> Install New Software&#8230;**를 실행후 &#8220;**http://www.baeyens.it/eclipse/update**&#8221; 주소를 입력하고 Add 버튼을 누른다. 그러면 **Arduino Eclipse extensions** 이 나타나는데 이것을 선택하면 설치가 된다.
  3. **Preferences > General > Workspace**를 선택하고 **&#8220;Save automatically before build&#8221;**를 선택 <img loading="lazy" class="alignnone" alt="" src="http://openmicrolab.cdn2.cafe24.com/eclipse_arduino1.png" width="780" height="612" />
  4. **Arduino**항목에서 **Arduino가 설치된 path와 library path** 를 입력하고, **Use Arduino ODE tools in eclipse**를 선택한다. 그리고 test serial dll를 클릭해서 serial drive가 동작하는 지 확인한다.<img loading="lazy" class="alignnone" alt="" src="http://openmicrolab.cdn2.cafe24.com/eclipse_arduino2.png" width="909" height="608" />
  5. 아두이노 프로젝트 만들기: **New >> Project >> Arduino >> New Arduino sketch**를 선택, 프로젝트 이름를 설정, 보드와 COM port를 설정하면 setup()과 loop()함수가 만들어진 빈 프로젝트가 생긴다.
  6. 간단한 blink 예제를 만들고 **Project >> Build All**하면 컴파일이되고, **AVR >> Upload Project to Target Devic**e를 선택하면 아두이노 보드에 프로그래밍이된다.<img loading="lazy" class="alignnone" alt="" src="http://openmicrolab.cdn2.cafe24.com/Arduino_Eclipse_Test.png" width="684" height="472" />