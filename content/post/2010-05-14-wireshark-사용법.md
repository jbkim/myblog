---
title: Wireshark 사용법
author: openmicrolab
type: post
date: 2010-05-14T11:50:07+00:00
url: /wireshark-사용법/
dsq_thread_id:
  - "1171306233"
categories:
  - Development
tags:
  - 패킷분석기 wireshark TCP/IP protocol

---
<span style="font-size: 10pt;"><span style="font-family: Gulim;"><span style="font-size: 10pt;">네트워크 관련 개발을 하다보면 패킷을 잡아야 할 때가 많습니다. 바로 이럴때 사용하는 툴이 WireShark 입니다.</span></span></span>  
<span style="font-size: 10pt;"><span style="font-family: Gulim;"><span style="font-size: 10pt;">물론 </span></span></span><a title="[http://www.wireshark.org]로 이동합니다." target="_blank" href="http://www.wireshark.org"><span style="font-size: 10pt;"><span style="font-family: Gulim;"><span style="font-size: 10pt;">www.wireshark.org</span></span></span></a><span style="font-size: 10pt;"><span style="font-family: Gulim;"><span style="font-size: 10pt;"> 에서 무료로 다운을 받을 수 있고요.</span></span></span><span style="font-size: 10pt;"><span style="font-family: Gulim;"><span style="font-size: 10pt;"><br /> Wiresahrk는 다양한 기능과 다양한 OS (Windows, OS X, Linux,<br /> and UNIX)에서 구동이 되기때문에 가장 인기있는 네트워크 프로토콜 분석기(network protocol analyzer) 이고. 게다가 GNU General Public License version 2를 따르며 오픈소스로 제공하고 있습니다. 원래는<br /> Ethereal이라는 프로그램이 있었는데, </span></span></span><span><span style="font-size: 10pt;"><span style="font-family: Gulim;"><span style="font-size: 10pt;">2006</span></span></span></span><span style="font-size: 10pt;"><span style="font-family: Gulim;"><span style="font-size: 10pt;">년 </span></span></span><span><span style="font-size: 10pt;"><span style="font-family: Gulim;"><span style="font-size: 10pt;">5</span></span></span></span><span style="font-size: 10pt;"><span style="font-family: Gulim;"><span style="font-size: 10pt;">월에 </span></span></span><span><span style="font-size: 10pt;"><span style="font-family: Gulim;"><span style="font-size: 10pt;">Gerald<br /> Combs</span></span></span></span><span style="font-size: 10pt;"><span style="font-family: Gulim;"><span style="font-size: 10pt;">라는</span></span></span><span><span style="font-size: 10pt;"><span style="font-family: Gulim;"><span style="font-size: 10pt;">ethereal 원</span></span></span></span><span style="font-size: 10pt;"><span style="font-family: Gulim;"><span style="font-size: 10pt;"> 개발자가 </span></span></span><span><span style="font-size: 10pt;"><span style="font-family: Gulim;"><span style="font-size: 10pt;">WinPcap</span></span></span></span><span style="font-size: 10pt;"><span style="font-family: Gulim;"><span style="font-size: 10pt;"> 으로 유명한 </span></span></span><span><span style="font-size: 10pt;"><span style="font-family: Gulim;"><span style="font-size: 10pt;">CACE</span></span></span></span><span style="font-size: 10pt;"><span style="font-family: Gulim;"><span style="font-size: 10pt;">라<br /> 는 회사에 입사하게 되어</span></span></span><span><span style="font-size: 10pt;"><span style="font-family: Gulim;"><span style="font-size: 10pt;">, 이 프로젝트는 Wireshark라고 이름이 바뀌게 된 것이라고 합니다. 현재는 대부분의<br /> 코아개발자들이 Wireshark에서 일한다고 하며</span></span></span></span><span><span style="font-size: 10pt;"><span style="font-family: Gulim;"><span style="font-size: 10pt;">, Ethereal</span></span></span></span><span style="font-size: 10pt;"><span style="font-family: Gulim;"><span style="font-size: 10pt;">은 현재 사이트도 존재는<br /> 하지만 실제적인 개발은 이루어 지고 있지 않습니다.</span></span></span><span><span style="font-size: 10pt;"><span style="font-family: Gulim;"><span style="font-size: 10pt;"><br /> 보다 자세한 내용은&nbsp;</span></span></span></span><span><span style="font-size: 10pt;"><span style="font-family: Gulim;"><span style="font-size: 10pt;">Wireshark<br /> 의 FAQ를 참고하세요.</span></span></span></span><span style="font-size: 10pt;"><span style="font-family: Gulim;"><span style="font-size: 10pt;"> </span></span></span>[<span style="font-size: 10pt;"><span style="font-family: Gulim;"><span style="font-size: 10pt;">http://www.wireshark.org/faq.html#q1.2</span></span></span>][1]<span style="font-family: Gulim;"><span style="font-size: 10pt;"><span style="text-decoration: underline;"><br /> </span>FAQ<br /> 에 보면 Wireshark는 어떤 shark인지? Wireshark를 어떻게 발음하는지도 나와 있습니다. 🙂</p> 

<p>
  </span></span><span style="font-family: Gulim;"><span style="font-size: 10pt;">일반적으로<br /> PC에는 1개이상의 네트워크 인터페이스가 있을 수 있으므로</span></span><span style="font-family: Gulim;"><span style="font-size: 10pt;"> 패킷을 잡기위해서는 먼저 네트워크 인터페이스를 선택을 해야 합니다.<br /> <img loading="lazy" src="/images/1/cfile28.uf.172151144BED377D22DB92.jpg" class="aligncenter" width="680" height="122" alt="" filename="Wireshark_1.jpg" filemime="image/jpeg" /><br /> 위와 같은 경우는 2번째 것을 선택 후 Start를 누르면 패킷이 잡힙니다. <br /> 요즘은 대부분의 허브가 스위칭 허브인데, 만약 장비에서 나오는 패킷을 잡기위해서는 중간에 더비허브를 사용해야 합니다.</p> 
  
  <p>
    물론 패킷을 잡아서 이것을 분석하는 능력도 있어야 겠죠. ^_^<br /> TCP/IP 및 네트워크 프로토콜 관련해서 잘 정리된 곳은 아래 사이트를 참고하세요.<br /> <a title="[http://www.tcpipguide.com/index.htm]로 이동합니다." target="_blank" href="http://www.tcpipguide.com/index.htm">http://www.tcpipguide.com/index.htm</a>
  </p>
  
  <p>
    </span></span>
  </p>
  
  <p>
    <span style="font-size: 10pt;"></span>
  </p>
  
  <p>
  </p>

 [1]: http://www.wireshark.org/faq.html#q1.2