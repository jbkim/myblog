---
title: '네트워크 패킷 생성기 (NPG: Network Packet Generator)'
author: openmicrolab
type: post
date: 2010-10-04T05:54:33+00:00
url: /네트워크-패킷-생성기-npg-network-packet-generator/
dsq_thread_id:
  - "1170218864"
categories:
  - Development
  - Tool
tags:
  - wireshark
  - 와이어샤크
  - NPG
  - packet generator
  - 패킷 생성기

---
<span style="font-size: 11pt; "><span style="font-size: 11pt; ">요즘은 제가 필요한 것을 인터넷에서 찾으면 다 있네요.&nbsp;</span></span><span class="Apple-style-span" style="line-height: 22px; font-size: 15px; "><span style="font-size: 11pt; ">누군가는 같은 고민을하고 고맙게도 만들었다는 사실&#8230; ^^</span></span>

<div>
  <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px;"><br /> </span></font>
</div>

<div>
  <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px;"><span style="font-size: 11pt; ">NPG는&nbsp;</span></span></font><span class="Apple-style-span" style="line-height: 22px; font-size: 15px; "><span style="font-size: 11pt; ">Winpcap을 사용하여 패킷을 보낼수 있는 </span></span><span class="Apple-style-span" style="line-height: 22px; font-size: 15px; "><span style="font-size: 11pt; ">윈도우즈 기반의 네트워크 패킷 생성기입니다. 즉 따로 프로그래밍을 하지 않고 원하는 패킷을 만들어서 보낼 수 있는 툴입니다. 사용법도 간단하고 옵션도 많지 않기 때문에 바로 사용이 가능합니다. GPL 라이센스이므로 자유롭게 사용이 가능하네요.</span></span>
</div>

<div>
  <span class="Apple-style-span" style="line-height: 22px; font-size: 15px; "><a href="http://www.wikistc.org/wiki/Network_packet_generator"><span style="font-size: 11pt; ">http://www.wikistc.org/wiki/Network_packet_generator</span></a><span style="font-size: 11pt; ">&nbsp;에 자세한 설명이 나와있고, 설치 파일은 이 페이지의 제일 아래보시면 다운받으실 수 있습니다.</span></span>
</div>

<div>
  <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px;"><br /> </span></font>
</div>

<div>
  <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px;"><span style="font-size: 11pt; "><b>사용법</b></span></span></font>
</div>

<div>
  <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px;"><span class="Apple-style-span" style="color: rgb(0, 0, 0); font-family: sans-serif; line-height: 19px; font-size: 13px; "></p> 
  
  <ul style="line-height: 1.5em; list-style-type: square; margin-top: 0.3em; margin-right: 0px; margin-bottom: 0px; margin-left: 1.5em; padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; list-style-image: url(http://www.wikistc.org/w/skins/monobook/bullet.gif); ">
    <li style="margin-bottom: 0.1em; ">
      <span style="font-size: 11pt; "><b>npg</b></span>
    </li>
    <li style="margin-bottom: 0.1em; ">
      <span style="font-size: 11pt; "><b>npg [-?hlw]</b></span>
    </li>
    <li style="margin-bottom: 0.1em; ">
      <span style="font-size: 11pt; "><b>npg [-vvvw] -fF <packet file name> -d <device interface></b></span>
    </li>
    <li style="margin-bottom: 0.1em; ">
      <span style="font-size: 11pt; "><b>npg [-rtvvv] -p <packet byte stream> -d <device interface></b></span>
    </li>
  </ul>
  
  <p>
    </span></span></font></div> 
    
    <div>
      <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px;"><br /> </span></font>
    </div>
    
    <div>
      <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px;"><span style="font-size: 11pt; ">NPG 프로그램을 다운받고 커맨드 창에서 아무런 옵션 없이 실행을 하면, 옵션을 물어보는데 대부분의 경우 옵션을 정하고, 보낼 패킷도 저장을해서 배치파일을 만들어서 테스트를 하는 것이 가장 손쉬운 방법입니다.</span></span></font>
    </div>
    
    <div>
      <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px;"><br /> </span></font>
    </div>
    
    <div>
      <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px;"><span style="font-size: 11pt; "><b>옵션</b></span></span></font>
    </div>
    
    <div>
      <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px;"></p> 
      
      <div>
        <span style="font-size: 11pt; "><b>-h 도움말 표시</b></span>
      </div>
      
      <div>
        <span style="font-size: 11pt; "><b>-d 패킷을 보낼 네트워크 디바이스를 선택</b></span>
      </div>
      
      <div>
        <span style="font-size: 11pt; "><b>-f &nbsp;패킷파일의 이름 지정</b></span>
      </div>
      
      <div>
        <span style="font-size: 11pt; "><b>-F Libpcap 호환 패킷파일 이름 지정</b></span>
      </div>
      
      <div>
        <span style="font-size: 11pt; "><b>-l 사용 가능한 네트워크 디바이스 나열</b></span>
      </div>
      
      <div>
        <span style="font-size: 11pt; "><b>-p <packet byte stream>&nbsp;인젝트할 패킷 바이트를 HEX 값으로 나열해주면 됨</b></span>
      </div>
      
      <div>
        <span style="font-size: 11pt; "><b>-r <repeat count> &nbsp;패킷을 몇번 반복할지 카운트를 지정</b></span>
      </div>
      
      <div>
        <span style="font-size: 11pt; "><b>-t <interval> 패킷을 인젝트 하기 전 시간 간격을 지정 (시간 기준은 밀리세컨드)</b></span>
      </div>
      
      <div>
        <span style="font-size: 11pt; "><b>-v, -vv, -vvv 동작 상태를 표시함 v 가 많을 수록 세부정보를 표시함</b></span>
      </div>
      
      <div>
      </div>
      
      <p>
        </span></font></div> 
        
        <div>
          <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px;"><span style="font-size: 11pt; ">실제로 보낼 데이터 파일을 가지고 설명을 하겠습니다.</span></span></font>
        </div>
        
        <div>
          <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px;"><span style="font-size: 11pt; ">아래 패킷 샘플은 <b>ARP request</b>를 하는 샘플입니다.</span></span></font>
        </div>
        
        <div>
          <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px;"><br /> </span></font>
        </div>
        
        <div style="line-height: 0.5; ">
          <font class="Apple-style-span" size="3"><span class="Apple-style-span" style="font-size: 13px; line-height: 22px;"></p> 
          
          <div class="txc-textbox" style="border-top-style: solid; border-right-style: solid; border-bottom-style: solid; border-left-style: solid; border-top-width: 1px; border-right-width: 1px; border-bottom-width: 1px; border-left-width: 1px; border-top-color: rgb(254, 222, 199); border-right-color: rgb(254, 222, 199); border-bottom-color: rgb(254, 222, 199); border-left-color: rgb(254, 222, 199); background-color: rgb(254, 222, 199); padding-top: 10px; padding-right: 10px; padding-bottom: 10px; padding-left: 10px; ">
            <span class="Apple-style-span" style="line-height: 18px; font-size: 12px; "></p> 
            
            <div style="line-height: 0.5; ">
              <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px; "><span style="font-size: 10pt; "><span style="font-size: 11pt; "><span style="font-size: 10pt; "># Generic example packets to demonstrate npg.exe&nbsp;</span></span></span></span></font>
            </div>
            
            <div style="line-height: 0.5; ">
              <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px; "><span style="font-size: 10pt; "><span style="font-size: 11pt; "><span style="font-size: 10pt; "># Current documentation an examples located @ http://www.wikistc.org/wiki/Network_packet_generator</span></span></span></span></font>
            </div>
            
            <div style="line-height: 0.5; ">
              <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px; "><br /> </span></font>
            </div>
            
            <div style="line-height: 0.5; ">
              <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px; "><span style="font-size: 10pt; "><span style="font-size: 11pt; "><span style="font-size: 10pt; "># TCP/IP ARP Request</span></span></span></span></font>
            </div>
            
            <div style="line-height: 0.5; ">
              <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px; "><span style="font-size: 10pt; "><span style="font-size: 11pt; "><span style="font-size: 10pt; ">[3, 1000] # 1000 밀리, 3 번 반복</span></span></span></span></font>
            </div>
            
            <div style="line-height: 0.5; ">
              <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px; "><span style="font-size: 10pt; "><span style="font-size: 11pt; "><span style="font-size: 10pt; "><ARP Request></span></span></span></span></font>
            </div>
            
            <div style="line-height: 0.5; ">
              <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px; "><span style="font-size: 10pt; "><span style="font-size: 11pt; "><span style="font-size: 10pt; ">{</span></span></span></span></font>
            </div>
            
            <div style="line-height: 0.5; ">
              <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px; "><span style="font-size: 10pt; "><span style="font-size: 11pt; "><span style="font-size: 10pt; "># Ethernet2 Header &#8212;&#8212;&#8212;</span></span></span></span></font>
            </div>
            
            <div style="line-height: 0.5; ">
              <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px; "><br /> </span></font>
            </div>
            
            <div style="line-height: 0.5; ">
              <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px; "><span style="font-size: 10pt; "><span style="font-size: 11pt; "><span style="font-size: 10pt; ">&nbsp;FF FF FF FF FF FF # Destination MAC</span></span></span></span></font>
            </div>
            
            <div style="line-height: 0.5; ">
              <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px; "><span style="font-size: 10pt; "><span style="font-size: 11pt; "><span style="font-size: 10pt; ">&nbsp;00 08 DC 01 01 12 # Source MAC</span></span></span></span></font>
            </div>
            
            <div style="line-height: 0.5; ">
              <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px; "><span style="font-size: 10pt; "><span style="font-size: 11pt; "><span style="font-size: 10pt; ">&nbsp;08 06 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; # Protocol ; ARP</span></span></span></span></font>
            </div>
            
            <div style="line-height: 0.5; ">
              <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px; "><br /> </span></font>
            </div>
            
            <div style="line-height: 0.5; ">
              <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px; "><span style="font-size: 10pt; "><span style="font-size: 11pt; "><span style="font-size: 10pt; "># ARP Header &#8212;&#8212;&#8212;&#8212;&#8212;</span></span></span></span></font>
            </div>
            
            <div style="line-height: 0.5; ">
              <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px; "><br /> </span></font>
            </div>
            
            <div style="line-height: 0.5; ">
              <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px; "><span style="font-size: 10pt; "><span style="font-size: 11pt; "><span style="font-size: 10pt; ">&nbsp;00 01 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; # Hardware type</span></span></span></span></font>
            </div>
            
            <div style="line-height: 0.5; ">
              <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px; "><span style="font-size: 10pt; "><span style="font-size: 11pt; "><span style="font-size: 10pt; ">&nbsp;08 00 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; # Protocol type</span></span></span></span></font>
            </div>
            
            <div style="line-height: 0.5; ">
              <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px; "><span style="font-size: 10pt; "><span style="font-size: 11pt; "><span style="font-size: 10pt; ">&nbsp;06 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;# Hardware size</span></span></span></span></font>
            </div>
            
            <div style="line-height: 0.5; ">
              <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px; "><span style="font-size: 10pt; "><span style="font-size: 11pt; "><span style="font-size: 10pt; ">&nbsp;04 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;# Protocol size</span></span></span></span></font>
            </div>
            
            <div style="line-height: 0.5; ">
              <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px; "><span style="font-size: 10pt; "><span style="font-size: 11pt; "><span style="font-size: 10pt; ">&nbsp;00 01 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; # Opcode : Request</span></span></span></span></font>
            </div>
            
            <div style="line-height: 0.5; ">
              <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px; "><span style="font-size: 10pt; "><span style="font-size: 11pt; "><span style="font-size: 10pt; ">&nbsp;00 08 DC 01 01 12 # Sender MAC address</span></span></span></span></font>
            </div>
            
            <div style="line-height: 0.5; ">
              <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px; "><span style="font-size: 10pt; "><span style="font-size: 11pt; "><span style="font-size: 10pt; ">&nbsp;c0 a8 0b c8 &nbsp; &nbsp; &nbsp; # Send IP</span></span></span></span></font>
            </div>
            
            <div style="line-height: 0.5; ">
              <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px; "><span style="font-size: 10pt; "><span style="font-size: 11pt; "><span style="font-size: 10pt; ">&nbsp;00 00 00 00 00 00 # Target MAC address</span></span></span></span></font>
            </div>
            
            <div style="line-height: 0.5; ">
              <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px; "><span style="font-size: 10pt; "><span style="font-size: 11pt; "><span style="font-size: 10pt; ">&nbsp;c0 a8 0b 64 &nbsp; &nbsp; &nbsp; # Target IP</span></span></span></span></font>
            </div>
            
            <div style="line-height: 0.5; ">
              <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px; "><br /> </span></font>
            </div>
            
            <div style="line-height: 0.5; ">
              <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px; "><span style="font-size: 10pt; "><span style="font-size: 11pt; "><span style="font-size: 10pt; "># Ethernet2 (Trailer) &#8212;&#8212;</span></span></span></span></font>
            </div>
            
            <div style="line-height: 0.5; ">
              <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px; "><br /> </span></font>
            </div>
            
            <div style="line-height: 0.5; ">
              <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px; "><span style="font-size: 10pt; "><span style="font-size: 11pt; "><span style="font-size: 10pt; ">&nbsp;00 00 00 00 00 00 # Trailer data</span></span></span></span></font>
            </div>
            
            <div style="line-height: 0.5; ">
              <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px; "><span style="font-size: 10pt; "><span style="font-size: 11pt; "><span style="font-size: 10pt; ">&nbsp;00 00 00 00 00 00&nbsp;</span></span></span></span></font>
            </div>
            
            <div style="line-height: 0.5; ">
              <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px; "><span style="font-size: 10pt; "><span style="font-size: 11pt; "><span style="font-size: 10pt; ">&nbsp;00 00 00 00 00 00</span></span></span></span></font>
            </div>
            
            <div style="line-height: 0.5; ">
              <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px; "><span style="font-size: 10pt; "><span style="font-size: 11pt; "><span style="font-size: 10pt; ">}</span></span></span></span></font>
            </div>
            
            <p>
              </span></div> 
              
              <div style="line-height: 0.5; ">
                <font class="Apple-style-span" size="3"><span class="Apple-style-span" style="font-size: 13px; line-height: 22px;"><br /> </span></font>
              </div>
              
              <p>
                <span style="font-size: 11pt; "><span style="font-size: 11pt; "><b>#</b> &nbsp;: 주석</span></span></span></font></div> 
                
                <div style="line-height: 0.5; ">
                  <font class="Apple-style-span" size="3"><span class="Apple-style-span" style="font-size: 13px; line-height: 22px;"><span style="font-size: 11pt; "><span style="font-size: 11pt; "><b>[]</b> : 패킷을 보낼 횟수 및 주기를 설정</span></span></span></font>
                </div>
                
                <div style="line-height: 0.5; ">
                  <font class="Apple-style-span" size="3"><span class="Apple-style-span" style="font-size: 13px; line-height: 22px;"><span style="font-size: 11pt; "><span style="font-size: 11pt; "><b><></b> : 어떤 패킷인지 나타내는 태크. 큰 의미는 없다.</span></span></span></font>
                </div>
                
                <div style="line-height: 0.5; ">
                  <font class="Apple-style-span" size="3"><span class="Apple-style-span" style="font-size: 13px; line-height: 22px;"><span style="font-size: 11pt; "><span style="font-size: 11pt; "><b>{}</b> : 실제로 보낼 패킷을 HEX값으로 적는다. 위 예에서와 같이 각각의 의미를 주석으로 표시하면 알아보기 쉽다.</span></span></span></font>
                </div>
                
                <div style="line-height: 0.5; ">
                  <font class="Apple-style-span" size="3"><span class="Apple-style-span" style="font-size: 13px; line-height: 22px;"><br /> </span></font>
                </div>
                
                <div style="line-height: 0.5; ">
                  <span class="Apple-style-span" style="line-height: 22px; font-size: 13px; "><span style="font-size: 11pt; "><span style="font-size: 11pt; ">위와 같이 파일을 만들고&nbsp;</span></span></span>
                </div>
                
                <div style="line-height: 0.5; ">
                  <span class="Apple-style-span" style="line-height: 22px; font-size: 13px; "></span><span class="Apple-style-span" style="line-height: 22px; font-size: 13px; "><span style="font-size: 11pt; "><span style="font-size: 11pt; "><b>npg -vv -f arp_request2.txt</b>를 입력하면 NPG 프로그램은 만든 패킷을 분석을 하고 이상이 없을 시 어떤 네트워크 디바이스를 써서 보낼지 물어봅니다. 선택을 숫자로 하면 패킷이 나갑니다.</span></span></span>
                </div>
                
                <div style="line-height: 0.5; ">
                  <font class="Apple-style-span" size="3"><span class="Apple-style-span" style="font-size: 13px; line-height: 22px;"><span style="font-size: 11pt; "><span style="font-size: 11pt; ">위 예에서는 패킷을 3번 1000밀리 주기로 보내는 옵션이므로 실제 패킷은 최초에 한번 나가고 추가적으로 1초 간격으로 패킷이 3개 더 나갑니다.</span></span></span></font>
                </div>
                
                <div style="line-height: 0.5; ">
                  <font class="Apple-style-span" size="3"><span class="Apple-style-span" style="font-size: 13px; line-height: 22px;"><br /> </span></font>
                </div>
                
                <div style="line-height: 0.5; ">
                  <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px; "><span style="font-size: 10pt; "></span></span></font>
                </div>
                
                <div>
                  <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px;"><br /> </span></font>
                </div>
                
                <div>
                  <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px;"><br /> </span></font>
                </div>
                
                <div>
                </div>
                
                <div>
                  <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px; "><br /> </span></font>
                </div>
                
                <div>
                  <font class="Apple-style-span" size="4"><span class="Apple-style-span" style="font-size: 15px; line-height: 22px;"><br /> </span></font></p> 
                  
                  <div>
                    <span style="font-size: 11pt; "><br /> </span>
                  </div>
                </div>
                
                <div id="__KO_DIC_LAYER__" style="padding-top: 0px; padding-right: 0px; padding-bottom: 0px; padding-left: 0px; position: fixed; z-index: 1e+009; overflow-x: hidden; overflow-y: hidden; border-top-width: 2px; border-right-width: 2px; border-bottom-width: 2px; border-left-width: 2px; border-top-style: solid; border-right-style: solid; border-bottom-style: solid; border-left-style: solid; border-top-color: rgb(51, 51, 119); border-right-color: rgb(51, 51, 119); border-bottom-color: rgb(51, 51, 119); border-left-color: rgb(51, 51, 119); display: none; ">
                </div>