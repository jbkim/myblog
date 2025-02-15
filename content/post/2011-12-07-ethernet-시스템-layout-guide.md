---
title: Ethernet 시스템 Layout guide
author: openmicrolab
type: post
date: 2011-12-07T10:04:53+00:00
url: /ethernet-시스템-layout-guide/
dsq_thread_id:
  - "1153949519"
categories:
  - Development
  - Network
tags:
  - Ethernet
  - Ethernet PHY
  - layout guide

---
임베디드 시스템에서 Ethernet은&nbsp;물리적으로 **Ethernet Controller + Magnetic + RJ45**로 이루어 진다.  
Ethernet Controller는&nbsp;다시 **Etherent MAC + PHY**로 구성이 되는데, Ethernet MAC의 경우 최근 MCU에 들어가 있는 경우가 많고 MAC/PHY칩으로 존재하기도 한다.  
Magnetic의 경우 코일이 감겨진 transformer를 얘기하는데 RJ45잭 안에 이 Magnetic이 들어가 있는 경우 흔히 MagJack이라고 불리운다. 사실 MagJack은 <A title="[http://www.belfuse.com/ProdList-MagJack.asp?pPrLinID=3&pPrLin=MagJack%20Connector%20Modules&pCat=ALL&pRCM=Y&pReset=Y&pOrder=BelPartNumber]로 이동합니다." href="http://www.belfuse.com/ProdList-MagJack.asp?pPrLinID=3&pPrLin=MagJack%20Connector%20Modules&pCat=ALL&pRCM=Y&pReset=Y&pOrder=BelPartNumber" target=_blank>BelFuse</A>사의 trade mark이다. PoE를 지원하는 MagJack의 경우 이전 <A title="[http://liketheocean.tistory.com/166]로 이동합니다." href="http://liketheocean.tistory.com/166" target=_blank>포스트</A>를 참고.  
임베디드 시스템에서 Ethernet의 하드웨어를 구현시 PCB 레이아웃을 할때는 PHY의 뒷단 부터는 신호의 무결성을 위해&nbsp;  
신경을 써야 한다. 대부분 PHY칩 업체의 가이드를 따르면 되며, 모든 벤더들의 가이드 역시 대동소이하다.

<DIV style="TEXT-ALIGN: left">
  <STRONG>Micrel사의 디자인 가이드<br /> </STRONG>
</DIV>

  


<P style="TEXT-ALIGN: left; MARGIN: 0px">
  <a href="/images/1/cfile4.uf.206119494EDEFD94288766.pdf" class="aligncenter" filename="AN-111 10-100 General PCB Design and Layout Guidelines.pdf"  filemime="application/pdf" />cfile4.uf.206119494EDEFD94288766.pdf</a><STRONG><br /> </STRONG>
</P>

  


<P style="TEXT-ALIGN: left; MARGIN: 0px">
  <STRONG>Davicom사의 디자인 가이드<br /> </STRONG><a href="/images/1/cfile9.uf.15635D494EDEFD94263063.pdf" class="aligncenter" filename="DM9161-LG-V01-052401s.pdf"  filemime="application/pdf" />cfile9.uf.15635D494EDEFD94263063.pdf</a><br /> <STRONG>IC Plus사의 디자인 가이드</STRONG>
</P>

  


<P style="TEXT-ALIGN: left; MARGIN: 0px">
  <a href="/images/1/cfile3.uf.186107494EDEFD9528439C.pdf" class="aligncenter" filename="IP101A layout guidelines Aug 27.pdf"  filemime="application/pdf" />cfile3.uf.186107494EDEFD9528439C.pdf</a><br /> <STRONG>Reaktek 사의 디자인 가이드</STRONG>
</P>

  


<P style="TEXT-ALIGN: left; MARGIN: 0px">
  <a href="/images/1/cfile24.uf.127843494EDEFD95061C16.pdf" class="aligncenter" filename="RTL8201BL_layoutguide.pdf"  filemime="application/pdf" />cfile24.uf.127843494EDEFD95061C16.pdf</a>
</P>