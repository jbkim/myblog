---
title: Eagle CAD로 작업한 PCB에 이미지 파일 넣기
author: openmicrolab
type: post
date: 2012-06-18T11:12:14+00:00
url: /eagle-cad로-작업한-pcb에-이미지-파일-넣기/
dsq_thread_id:
  - "1156688616"
categories:
  - Open Source Hardware
tags:
  - EagleCAD
  - Eagle CAD ulp
  - eagle cad logo

---
Eagle CAD로&nbsp;PCB작업을 하다보면 회사 로고 같은 이미지를 PCB에 넣을 때가 있다.

방법은 다음과 같다.



1.&nbsp;원하는 그림을 그림판에서 불러와서 단색 BMP로 저장을 한다.

2. 새로 프로젝트를 만들고, 보드 파일을 연후에 , File > Run > &#8220;import-bmp.ulp&#8221;을 실행한다.

3. 윈도우가 하나 뜨면 OK버튼을 누르고, BMP 파일을 불러온다.

4. 단색 BMP로 저장을 했기 때문에 다음과 같이 사용할 색깔이 2가지 색으로 나온다.

&nbsp; &nbsp;검적색으로 된 부분만 필요하므로 검정색만 선택을 한다.



<p style="text-align: center; clear: none; float: none; ">
  <img loading="lazy" src="/images/1/cfile23.uf.137C073E4FDF03610C6CBD.png" class="aligncenter" width="356" height="166" filename="eagle_bmp_1.png" filemime="image/jpeg" style="""" />
</p>



5. 이미지 파일에 대해 지정하는 옵션이다. 사이즈를 조정하는 것과, 레이어를 선택하는 옵션이다. 아무 선택도 하지 않으며면 200번째 레이어에 1:1로 이미지가 들어간다.

<p style="text-align: center; clear: none; float: none; ">
  <img loading="lazy" src="/images/1/cfile27.uf.20552E3C4FDF037D0B39DE.png" class="aligncenter" width="299" height="484" filename="eagle_bmp_2.png" filemime="image/jpeg" style="width: 299px; height: 484px; " />
</p>



6. Run script를 클릭한다.&nbsp;

&nbsp; &nbsp;이 스크립트가 실행이 되면 다음과 같이 보드파일에 BMP 파일이 레이어 200에 표시가 된다.

<p style="text-align: center; clear: none; float: none; ">
  <img loading="lazy" src="/images/1/cfile25.uf.1278BD464FDF0C4C1CB33E.png" class="aligncenter" width="340" height="375" filename="eagle_bmp_3.png" filemime="image/jpeg" style="width: 340px; height: 375px; " />
</p>



7. 나중에도 이것을 사용하기 위해 라이브러리도 만들어 놓으면 편하다.&nbsp;

&nbsp; &nbsp; 이 로고 파일을 Group으로 선택을 한후 Copy한다.



8. Control Panel에서 라이브러리를 하나 만들고 Package에서 새로운 Package를 만든다.

&nbsp; &nbsp;여기서 Edit > Paste를 하면 된다.

&nbsp; &nbsp;이 라이브러리의 symbol은 박스 하나 정도로 간단히 만들면 다른 프로젝트에서도 계속해서 사용이 가능하다.