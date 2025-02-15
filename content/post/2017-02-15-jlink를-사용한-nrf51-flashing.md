---
title: Jlink를 사용한 nRF51 flashing
author: openmicrolab
type: post
date: 2017-02-15T03:21:29+00:00
url: /jlink를-사용한-nrf51-flashing/
categories:
  - Bluetooth
tags:
  - nordic
  - Jlink
  - nRF51
  - bluetoorh

---
지난번 <a href="http://openmicrolab.com/mac-os-x%EC%97%90-nrf51-%EA%B0%9C%EB%B0%9C-%ED%99%98%EA%B2%BD-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0/" target="_blank">nRF51개발 환경 포스팅</a>에 빠진 부분인 flashing 부분

**nrfjprog &#8211; Programming Tool**

nrfjprog는 nRF5x-Command-Line-Tools의 번들 프로그램으로 SWD를 이용해 펌웨어 이미지를 로딩한다.

**nrfjprog:**

<pre class="prettyprint prettyprinted"><code>&lt;span class="com">/* Optional: erase target if not already blank */&lt;/span>
&lt;span class="pln">nrfjprog &lt;/span>&lt;span class="pun">--&lt;/span>&lt;span class="pln">family &lt;/span>&lt;span class="pun">&lt;&lt;/span>&lt;span class="pln">nRF51&lt;/span>&lt;span class="pun">/&lt;/span>&lt;span class="lit">52&lt;/span>&lt;span class="pun">&gt;&lt;/span> &lt;span class="pun">-&lt;/span>&lt;span class="pln">e 
&lt;/span>&lt;span class="com">/* Load FW image to target */&lt;/span>
&lt;span class="pln">nrfjprog &lt;/span>&lt;span class="pun">--&lt;/span>&lt;span class="pln">family &lt;/span>&lt;span class="pun">&lt;&lt;/span>&lt;span class="pln">nRF51&lt;/span>&lt;span class="pun">/&lt;/span>&lt;span class="lit">52&lt;/span>&lt;span class="pun">&gt;&lt;/span> &lt;span class="pun">--&lt;/span>&lt;span class="pln">program _build&lt;/span>&lt;span class="pun">/&lt;&lt;/span>&lt;span class="pln">name&lt;/span>&lt;span class="pun">&gt;.&lt;/span>&lt;span class="pln">hex
&lt;/span>&lt;span class="com">/* Reset and run */&lt;/span>    
&lt;span class="pln">nrfjprog &lt;/span>&lt;span class="pun">--&lt;/span>&lt;span class="pln">family &lt;/span>&lt;span class="pun">&lt;&lt;/span>&lt;span class="pln">nRF51&lt;/span>&lt;span class="pun">/&lt;/span>&lt;span class="lit">52&lt;/span>&lt;span class="pun">&gt;&lt;/span> &lt;span class="pun">-&lt;/span>&lt;span class="pln">r&lt;/span></code></pre>

**JlinkExe:**

<pre class="prettyprint prettyprinted"><code>&lt;span class="com">/* Open Jlink Commander from terminal in _build directory */&lt;/span> 
&lt;span class="typ">JLinkExe&lt;/span> &lt;span class="pun">-&lt;/span>&lt;span class="pln">device &lt;/span>&lt;span class="pun">&lt;&lt;/span>&lt;span class="pln">nRF51&lt;/span>&lt;span class="pun">/&lt;/span>&lt;span class="pln">nRF52&lt;/span>&lt;span class="pun">&gt;&lt;/span>
&lt;span class="pun">&gt;&lt;/span>&lt;span class="pln"> erase &lt;/span>&lt;span class="com">// Optional: erase target if not already blank&lt;/span>
&lt;span class="pun">&gt;&lt;/span>&lt;span class="pln"> loadfile &lt;/span>&lt;span class="str">&lt;name&gt;&lt;/span>&lt;span class="pun">.&lt;/span>&lt;span class="pln">hex &lt;/span>&lt;span class="com">// loads FW&lt;/span>
&lt;span class="pun">&gt;&lt;/span>&lt;span class="pln"> r &lt;/span>&lt;span class="com">// Reset and halt&lt;/span>
&lt;span class="pun">&gt;&lt;/span>&lt;span class="pln"> g &lt;/span>&lt;span class="com">// Run&lt;/span>
&lt;span class="pun">&gt;&lt;/span>&lt;span class="pln"> q &lt;/span>&lt;span class="com">// Exit&lt;/span></code></pre>

> <p class="p1">
>   <span class="s1">JlinkExe -device nrf51822_xxaa -if swd -speed 4000</span>
> </p>