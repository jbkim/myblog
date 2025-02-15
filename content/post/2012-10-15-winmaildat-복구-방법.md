---
title: winmail.dat 복구 방법
author: openmicrolab
type: post
date: 2012-10-15T05:06:18+00:00
url: /winmaildat-복구-방법/
dsq_thread_id:
  - "1164746887"
categories:
  - Development
  - Tool
tags:
  - TNEF
  - winmail.dat
  - 맥용 아웃룩
  - 아웃룩

---
Mac&nbsp;OS X에서 마이크로 소프트 아웃룩을&nbsp;사용중이다.&nbsp;

기존 Windows의&nbsp;아웃룩과의 호환성 때문에 메일에&nbsp;winmail.dat파일이 첨부가 되어온다.&nbsp;

이것의 원인은 마이크로소프트의 support에 의하면&nbsp;다음과 같다.

<a href="http://support.microsoft.com/kb/278061/ko" target="_blank" class="tx-link">http://support.microsoft.com/kb/278061/ko</a>

즉 아웃룩에서 서식있는 텍스트 형식(RTF)로 메일을 보낼때 이런 경우가 발생을 하는데, 메일을 수신 하는 측에서 RTF를 지원하지 않는 경우에 이것을 보완하기 위해 자신들만의 포맷인 TNEF(Transport Neutral Encapsulation Format)으로 보내기 때문이다.&nbsp;

해결 방법은 보내는 측에 일반 텍스트 형태로 메일을 다시 보내달라는 방법과

winmail.dat를 복구하는 프로그램을 사용하면 된다. 물론 100% 복구되는 지는 잘 모르겠지만, Mac OS X용으로는 TNEF&#8217;s Enough가 있다.

<a href="http://www.joshjacob.com/mac-development/tnef.php" target="_blank" class="tx-link">http://www.joshjacob.com/mac-development/tnef.php</a>



<p style="text-align: center; ">
  Version 3.2.1 for Mac IS X 10.6/107(Intel only)버젼 첨부
</p>

<p style="text-align: center; ">
  <a href="/images/1/cfile6.uf.114D7337507B98FC308623.dmg" class="aligncenter" filename="TNEF3.2.1.dmg" filemime="application/octet-stream" />cfile6.uf.114D7337507B98FC308623.dmg</a>
</p>