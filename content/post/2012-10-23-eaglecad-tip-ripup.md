---
title: 'EagleCAD Tip- Ripup'
author: openmicrolab
type: post
date: 2012-10-23T05:03:13+00:00
url: /eaglecad-tip-ripup/
dsq_thread_id:
  - "1128991572"
categories:
  - Tip
tags:
  - EagleCAD
  - Ripup

---
EagleCAD를 쓰다보면 기능은 있는데, 메뉴에 나와 있지 않아서 접근이 힘든 경우가 있다. &nbsp;대부분이 &nbsp;Edit Commands 기능들이다. 이럴땐 &nbsp;Help를 찾아보거나&nbsp;열심히 구글링하거나&#8230;&#8230;

여기에 정리하는 이유는 나중에 찾기 쉽게하기 위해&#8230; ^^*



<p style="text-align: center; clear: none; float: none; ">
  <img loading="lazy" src="/images/1/cfile3.uf.11300349508625CF1C214F.PNG" class="aligncenter" width="480" height="180" filename="ripup.PNG" filemime="image/jpeg" />
</p></p> 

**<span style="font-size: 10pt; ">Ripup</span>**

<font size="2"><span style="line-height: 19px;"><b>작업한 라우팅을 날려버릴때 사용한다.</b></span></font>

<font size="2"><span style="line-height: 19px;"><b>만약 라우팅 전부를 없애고 싶으면, &nbsp;&#8220;<span style="background-color: rgb(255, 228, 0); ">Ripup;</span>&#8221; 하면 된다.</b></span></font>

<font size="2"><span style="line-height: 19px;"><b><br /></b></span></font>

<font size="2"><span style="line-height: 19px;"><b><br /></b></span></font></p> 

<p style="margin-left: 0px; margin-right: 0px; ">
  <span style=" font-weight:600;">Function</span>
</p>

<p style="margin-left: 30px; margin-right: 0px; ">
  Changes routed wires and vias into airwires.<br />Changes the display of polygons to &#8220;outlines&#8221;.
</p>

<p style="margin-left: 0px; margin-right: 0px; ">
  <span style=" font-weight:600;">Syntax</span>
</p>

<p style="margin-left: 30px; margin-right: 0px; ">
  <span style=" font-family:'Courier New,courier';">RIPUP;</span><br /><span style=" font-family:'Courier New,courier';">RIPUP [ @ ] [ ! ] •..</span><br /><span style=" font-family:'Courier New,courier';">RIPUP [ @ ] [ ! ] signal_name..</span>
</p>

<p style="margin-left: 0px; margin-right: 0px; ">
  <span style=" font-weight:600;">Mouse keys</span>
</p>

<p style="margin-bottom: 8px; margin-left: 30px; margin-right: 0px; ">
  <span style=" font-family:'courier'; font-weight:600; background-color:#eeeeee;">Ctrl+Right</span> rips up the group.
</p>

<p style="margin-left: 0px; margin-right: 0px; ">
  <span style=" font-weight:600;">See also</span> <a href="#43"><span style=" text-decoration: underline; color:#0000ff;">DELETE</span></a>, <a href="#55"><span style=" text-decoration: underline; color:#0000ff;">GROUP</span></a>, <a href="#79"><span style=" text-decoration: underline; color:#0000ff;">POLYGON</span></a>, <a href="#83"><span style=" text-decoration: underline; color:#0000ff;">RATSNEST</span></a>
</p>

<p style="margin: 12px 0px; ">
  The RIPUP command changes routed wires (tracks) into airwires. That can be done for:
</p>

<ul style="margin-top: 0px; margin-bottom: 0px; margin-left: 0px; margin-right: 0px; -qt-list-indent: 1;">
  <li style="margin: 12px 0px 0px; ">
    all signals (RIPUP;)
  </li>
  <li style="margin: 0px; ">
    all signals except certain ones (e.g. RIPUP ! GND VCC;)
  </li>
  <li style="margin: 0px; ">
    one or more signals (e.g. RIPUP D0 D1 D2;)
  </li>
  <li style="margin: 0px; ">
    certain segments (chosen with one or more mouse clicks)
  </li>
  <li style="margin: 0px; ">
    all polygons (RIPUP @;)
  </li>
  <li style="margin: 0px; ">
    all polygons of certain signals (e.g. RIPUP @ GND VCC;)
  </li>
  <li style="margin: 0px 0px 12px; ">
    all polygons except those of certain signals (e.g. RIPUP @ ! GND VCC;)
  </li>
</ul>

<p style="margin-left: 0px; margin-right: 0px; ">
</p></p>