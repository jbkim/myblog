---
title: 'SDCC  putchar 버그 수정'
author: openmicrolab
type: post
date: 2011-06-01T08:13:29+00:00
url: /sdcc-putchar-버그-수정/
dsq_thread_id:
  - "1204825980"
categories:
  - Open Source Hardware
tags:
  - "8051"
  - SDCC
  - printf
  - W7100A
  - 무료컴파일러

---
지난번 포스팅때 <A title="[http://liketheocean.tistory.com/83]로 이동합니다." href="http://liketheocean.tistory.com/83" target=_blank>8051 무료 컴파일러인 SDCC</A>를 소개했었고, 이를 이용해서 <A title="[http://liketheocean.tistory.com/84]로 이동합니다." href="http://liketheocean.tistory.com/84" target=_blank>W7100 TCP loopback 코드까지 </A>만들어 봤었다.  
이미 그때도 printf가 잘 안되어서 이상하다고 했었는데, 이번에 telnet 코드를 포팅하면서 문제를 해결했다.  
문제는 SDCC 컴파일러가 제대로 C 코드를 ASM으로 변환을 해주지 못하는게 원인&#8230; 역시 무료 컴파일러라서 그런가???

<DIV style="BORDER-BOTTOM: #c1c1c1 1px dashed; BORDER-LEFT: #c1c1c1 1px dashed; PADDING-BOTTOM: 10px; BACKGROUND-COLOR: #eeeeee; PADDING-LEFT: 10px; PADDING-RIGHT: 10px; BORDER-TOP: #c1c1c1 1px dashed; BORDER-RIGHT: #c1c1c1 1px dashed; PADDING-TOP: 10px" class=txc-textbox>void putchar (char c)&nbsp;  
{  
&nbsp; SBUF = c;  
&nbsp; while(!TI);  
&nbsp; TI = 0;  
}  
</DIV>  
위&nbsp;putchar 함수가 어셈으로 변환된 코드를 보니 TI = 0 을 CLR TI 로 변환을 하지 않네요.  
그래서 다음과 같이 inline assembler를 사용해서 수정을 하니 잘 동작을 합니다.

<DIV style="BORDER-BOTTOM: #c1c1c1 1px dashed; BORDER-LEFT: #c1c1c1 1px dashed; PADDING-BOTTOM: 10px; BACKGROUND-COLOR: #eeeeee; PADDING-LEFT: 10px; PADDING-RIGHT: 10px; BORDER-TOP: #c1c1c1 1px dashed; BORDER-RIGHT: #c1c1c1 1px dashed; PADDING-TOP: 10px" class=txc-textbox>void putchar (char c)&nbsp;  
{  
&nbsp;SBUF = c;  
&nbsp;while(!TI);  
<FONT color=#e31600>__asm&nbsp;  
&nbsp;clr TI  
__endasm;  
</FONT>}  
</DIV>  
W7100A에 telnet server code를 SDCC로 포팅한 코드로 첨부.

<P style="MARGIN: 0px">
  <a href="/images/1/cfile29.uf.181ED1344DE5F44423398E.zip" class="aligncenter" filename="telnet_sdcc.zip"  filemime="application/zip" />cfile29.uf.181ED1344DE5F44423398E.zip</a>
</P>