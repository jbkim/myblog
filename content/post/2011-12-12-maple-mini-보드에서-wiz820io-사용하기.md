---
title: Maple mini 보드에서 Wiz820io 사용하기
author: openmicrolab
type: post
date: 2011-12-12T10:00:00+00:00
url: /maple-mini-보드에서-wiz820io-사용하기/
dsq_thread_id:
  - "1183921163"
categories:
  - Wiznet
tags:
  - wiz820io
  - Leaflabs
  - maple
  - maple mini

---
<P style="MARGIN: 0px">
  <A title="[http://leaflabs.com/]로 이동합니다." href="http://leaflabs.com/" target=_blank>Leaflab</A>사의 <A title="[http://leaflabs.com/2011/10/wizzin-through-the-ether-net/]로 이동합니다." href="http://leaflabs.com/2011/10/wizzin-through-the-ether-net/" target=_blank>블로그</A>를 보고 Maple mini보드에 <A title="[http://www.wiznet.co.kr/wiz820io]로 이동합니다." href="http://www.wiznet.co.kr/wiz820io" target=_blank>Wiz820io</A>를 연결해서 테스트를 진행했다. 브레드보드가 있으니 연결은 금방한다. 예제들이 UART3를 사용하기 때문에 아래 그림처럼 RS232 트랜시버가 달려있는 쪽보드를 사용해서 시리얼을 연결했다. <br /> <img loading="lazy" src="/images/1/cfile5.uf.195BA43E4EE5A0B1143718.jpg" class="aligncenter" width="483" height="338" alt="" filename="maple mini test.jpg" filemime="image/jpeg" />
</P>

  


<P style="MARGIN: 0px">
  <STRONG>H/W 연결</STRONG><br /> Maple mini보드의 Fritzing라이브러리도 만들고&#8230; 회로 연결은 아래 그림과 같다. 사실 연결할 것은 SPI 시그널과 VCC, GND 밖에 없다.&nbsp;<br /> &nbsp;&nbsp;&nbsp; <STRONG>Maple mini Fritzing 라이브러리:</P><br /> 
  
  <P style="MARGIN: 0px">
    <a href="/images/1/cfile4.uf.1460D83F4EE5A5580D181E.fzpz" class="aligncenter" filename="maple mini.fzpz"  filemime="application/zip" />cfile4.uf.1460D83F4EE5A5580D181E.fzpz</a></STRONG><br /> <img loading="lazy" src="/images/1/cfile22.uf.135BA43E4EE5A0B316548A.PNG" class="aligncenter" width="463" height="407" alt="" filename="maple_mini_Wiz820io.PNG" filemime="image/jpeg" /><STRONG>라이브러리</STRONG><br /> 아래 첨부한 파일을 Leaflab IDE의 \libraries\wizEthernet에 압축을 풀어서 넣는다.<br /> 예제 파일이 telnetServer, webServer 2가지가 있는데, 제공되는 예제가 약간 문제가 있다.<br /> telentServer의 경우 password를 칠때는 문제가 없지만 다른 경우에 매 문자마다 echo back를 해서 이것을 수정을 했고, webServer의 경우 브라우져에서 favicon을 요청시 처리를 위해 &#8220;HTTP/1.1 404 Not Found&#8221; 페이지를 돌려주기 위한 코드를 추가 했다.&nbsp;<br /> <STRONG>&nbsp;&nbsp;&nbsp;wizEthernet 라이브러리:&nbsp;</P><br /> 
    
    <P style="MARGIN: 0px">
      <a href="/images/1/cfile29.uf.175DF13F4EE5A4850D2B13.zip" class="aligncenter" filename="wizEthernet.zip"  filemime="application/zip" />cfile29.uf.175DF13F4EE5A4850D2B13.zip</a>
    </P>
    
    <br /> 
    
    <P style="MARGIN: 0px">
      </STRONG><br /> <STRONG>&nbsp; 수정된 예제 파일: </P><br /> 
      
      <P style="MARGIN: 0px">
        <a href="/images/1/cfile3.uf.172F71414EE5A4430F27EA.pde" class="aligncenter" filename="telnetserver.pde"  filemime="text/x-c; charset=us-ascii" />cfile3.uf.172F71414EE5A4430F27EA.pde</a>
      </P>
      
      <br /> 
      
      <P style="MARGIN: 0px">
        <a href="/images/1/cfile27.uf.17335D414EE5A4542CA563.pde" class="aligncenter" filename="webserver.pde"  filemime="text/x-c; charset=us-ascii" />cfile27.uf.17335D414EE5A4542CA563.pde</a>
      </P>
      
      <br /> 
      
      <P style="MARGIN: 0px">
        <br /> </STRONG><br /> 혹시 컴파일후 보드에 다운로그가 문제가 있을 경우, 이전 포스트를 참고(<A title="[http://liketheocean.tistory.com/174]로 이동합니다." href="http://liketheocean.tistory.com/174" target=_blank>LeafLabs의 Maple mini, Maple Ret 5 보드 사용기</A>)
      </P></p>