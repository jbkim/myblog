---
title: CoolTerm에 custom baudrate 추가하는 법
author: openmicrolab
type: post
date: 2016-01-12T07:09:46+00:00
url: /coolterm에-custom-baudrate-추가하는-법/
featured_image: /wp-content/uploads/2016/01/Coolterm-100x100.png
categories:
  - Development
  - Tool
tags:
  - CoolTerm
  - custom baudrate

---
Mac OS X에서 유일하게 사용하고 있는 시리얼 터미널 프로그램인 <a href="http://freeware.the-meiers.org/" target="_blank">CoolTerm</a>은 무료인데다가 웬만한 기능은 다있어서 개발할때 주로 사용을 한다. 그런데 일반적인 baudrate가 아닌 경우에 코드를 수정해서 테스트를 했는데 그럴 필요가 없다. 왜냐면 CoolTerm이 custom baudrate를 지원한다.

### **CoolTerm에 custom baudrate 추가하는 법**

CoolTerm이 설치되어 있는 폴더에 **baudrates.ini**파일을 하나 만들고 필요한 baudrate를 입력한다. 즉 다음과 같이 입력을 하면, 기존에 설정된 baudrate에 추가로 입력된 baudrate가 생성이 된다.

> 100  
> 110  
> 150  
> 128000  
> 153600  
> 256000  
> 460800  
> 921600

아래 그림은 250000을 추가후 실행한 모습  
[<img loading="lazy" class="aligncenter size-full wp-image-3493" src="/images/2016/01/Coolterm.png" alt="Coolterm" width="800" height="670" srcset="/images/2016/01/Coolterm.png 800w, /images/2016/01/Coolterm-300x251.png 300w" sizes="(max-width: 800px) 100vw, 800px" />][1]

 [1]: /images/2016/01/Coolterm.png