---
title: 큐라 한글화 – Cura Korean Translation
author: openmicrolab
type: post
date: 2014-09-19T07:58:07+00:00
url: /큐라-한글화-cura-korean-translation/
dsq_thread_id:
  - "3032509641"
categories:
  - 3D Printer
tags:
  - Cura
  - 큐라
  - 3d Print
  - 큐라 한글번역

---
<img loading="lazy" class="alignnone" src="http://openmicrolab.cdn2.cafe24.com/Cura_Hangul_Win.png" alt="" width="767" height="485" />

네이버 카페에서 누군가 큐라(Cura)를 한글화한 것을 몇 건을 봤는데, po파일을 찾을 수 가 없고 또 어떤 것은 파이썬 소스의 영문을 그대로 건드려서 이건 아니다 싶어서 한글 번역을 했다. 사실 한글 번역은 귀찮은 작업인데 이런 작업을 하면서 더 알아가는 것도 있고 오픈소스에 기여를 하는 한 방편이기도 해서 진행을 했다.

<img loading="lazy" class="alignnone" src="http://openmicrolab.cdn2.cafe24.com/LC_MESSAGES.png" alt="" width="709" height="263" /> 

> <del>일단 기존에 사용하는 큐라를 한글로 바꾸려면 Cura설치폴더\Cura\resources\locale 폴더에 위에서 받은 파일중 ko 폴더를 추가하고 큐라가 설치된 폴더아래 Cura 폴더 아래의 </del>**<del>preferences.ini 파일에서 language 항목에 Korean으로 설정하면 된다.</del>  14.09버젼 부터는 언어 설정을 하는 옵션이 추가됨**

<img loading="lazy" class="alignnone" src="http://openmicrolab.cdn2.cafe24.com/Cura_Preference.png" alt="" width="461" height="450" /> 

> 그리고 Cura 설치폴더\Cura\util\resources.py 파일에 다음과 같이 Korean을 추가한다.

<img loading="lazy" class="alignnone" src="http://openmicrolab.cdn2.cafe24.com/cura_resources.png" alt="" width="317" height="160" /> 

혹시 누군가 이런 작업을 할 때 필요할 것 같아서 어떻게 한글화를 하는지에 대해 간단히 정리를 한다.

  * <a href="https://github.com/jbkim/Cura" target="_blank">github</a>에서 파일을 다운로드(github 우측 하단의 &#8220;Download ZIP&#8221;) 받거나, fork
  * 다운로드 받은 코드에서 Cura\resources\locale\ko 폴더를 Cura.po 파일을 <a href="http://poedit.net/" target="_blank">PoEdit</a> 같은 프로그램으로 열어서 한글 수정
  * ./update_translation.sh 스크립트를 실행
  * ./package.sh 스크립트를 실행
  * **큐라 한글 버젼실행 파일 <del>(<a href="https://www.dropbox.com/s/ic3wqvfi6zr6kxb/Cura_14.08.1-RC2.exe?dl=0" target="_blank">Cura_14.08.1-RC2</a>) 다운로드 받기</del> &#8211; 프로그램 설치 후 First time run Wizard에서 언어를 Korean을 설정하면 한글로 설정이 된다. <a href="https://www.dropbox.com/s/f5hc16gzd1398rn/Cura_14.09.exe?dl=0" target="_blank">14.09 버전다운로드</a>, <a href="http://openmicrolab.com/%ED%81%90%EB%9D%BC-%ED%95%9C%EA%B8%80%ED%99%94-14-09-%EB%B2%84%EC%A0%84/" target="_blank">관련 포스팅</a>**

일단 Ultimaker의 Cura쪽에 full request를 해서 merge가 됐으니, 다음 버젼에서는 한글이 나올 수도&#8230;  그리고 윈도우즈/리눅스 및 맥에서 큐라 배포버젼을 만드는 방법은 다음 포스트에서 정리&#8230;