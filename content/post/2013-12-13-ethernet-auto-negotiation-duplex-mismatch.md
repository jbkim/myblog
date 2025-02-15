---
title: Ethernet Auto negotiation – Duplex mismatch
author: openmicrolab
type: post
date: 2013-12-13T09:13:17+00:00
url: /ethernet-auto-negotiation-duplex-mismatch/
dsq_thread_id:
  - "2047637961"
categories:
  - Development
  - Network
tags:
  - Ethernet
  - Ethernet PHY
  - auto negotiation
  - duplex mismatch

---
이더넷 네트워크에서 auto negotiation은 PHY에서 담당하는 기능으로 전송선로상에서 상대방(peer)의 속도 및 half/ full duplex여부를 자동으로 결정하는 plug and play  같은 기능이다. 이 기능은 1997년에 Fast Ethernet IEEE802.3u 표준으로 들어갔고, 1999년에 Gigabit Ethenet 802.3ab 표준이 되었다.

Fast Ethernet 일 경우 1)양쪽이 auto일 경우 2) auto &#8211; 10/100 고정일 경우 3) 10/100고정 &#8211; 10/100 고정일 경우가 발생한다. 양쪽이 auto negotiation일 경우는 속도가 높고 duplex쪽으로 잡힌다. 즉 다음과 같은 우선 순위에 의해 속도 및 duplex가 결정이 된다.

  1. 1000BASE-T full duplex
  2. 1000BASE-T half duplex
  3. 100BASE-T2 full duplex
  4. 100BASE-TX full duplex
  5. 100BASE-T2 half duplex
  6. 100BASE-T4
  7. 100BASE-TX half duplex
  8. 10BASE-T full duplex
  9. 10BASE-T half duplex

하지만 한쪽만 auto이고 다른 한 쪽이 10/100으로 고정을 할 경우 속도는 10/100잘 설정이 되는데 duplex에 문제가 발생할 수 있다. 여러 경우의 수 중에서 duplex에 문제가 생기는 경우는 한쪽이 Full Duplex인 경우이다.

> 즉 한쪽이 auto-negotiation으로 설정이 되어 있고, 다른 쪽이 full duplex일 경우 full duplex로 잡힐것 같지만 그렇지 않다. **이 경우는 하위 호환성을 해 무조건 half-duplex로 잡힌다는 사실&#8230;**

관련 자료

<a href="http://e2epi.internet2.edu/case-studies/SC02/DuplexMismatch.html" target="_blank">http://e2epi.internet2.edu/case-studies/SC02/DuplexMismatch.html</a>

<a href="http://en.wikipedia.org/wiki/Autonegotiation" target="_blank">http://en.wikipedia.org/wiki/Autonegotiation</a>

<a href="http://en.wikipedia.org/wiki/Duplex_mismatch" target="_blank">http://en.wikipedia.org/wiki/Duplex_mismatch</a>

<a href="http://e2epi.internet2.edu/case-studies/SC02/DuplexMismatch.html" target="_blank">[wpdm_file id=9] </a>