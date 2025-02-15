---
title: Arduino 코드에서 WIZnet칩 구별하기
author: openmicrolab
type: post
date: 2014-03-01T08:41:49+00:00
url: /arduino-코드에서-wiznet칩-구별하기/
dsq_thread_id:
  - "2364719943"
categories:
  - Open Source Hardware
  - Development
  - Wiznet
tags:
  - Arduino
  - 아두이노
  - WIZNET
  - Ethernet Shield

---
### WIZnet 칩

WIZnet 칩중에서 SPI가 지원되는 칩은 W5100, W5200 그리고 W5500이 있다. 이중 W5100은 아두이노에 적용이 되어 Ethernet Shield 및 Arduino Ethernet 보드에 사용이 되고 있다. 물론 W5200으로 만든 Ethernet Shield도 있고 W5500으로 만든 Ethernet Shield도 있다. 그리고 최근에는 아두이노 팀에서 W5500으로 Ethernet Shield를 만들고 있다. 이렇게 3가지 칩으로 적용된 보드가 있는데, 그럼 코드에서 이 칩들을 구별할 수 있는 방법이 있는가?

### Arduino 코드에서 WIZnet칩 구별하기

W5100, W5200, W5500의 칩들의 기본 기능은 같지만 H/W적으로는 패키지도 다르고 핀도 다르고, 내부 메모리 맵도 다르다. 모두 SPI 를 사용하지만 칩을 제어하기 위한 SPI format도 다르다. 그리고 W5100은 소켓이 4개이고 나머지 칩들은 모두 8개의 소켓을 지원한다.

코드에서 이들 칩을 구별을 하려면 이 칩들의 내부 레지스터를 읽어서 각 칩들에만 유효한 값을 확인해서 비교를 해야한다. 다행히 W5200과 W5500은 칩의 버젼을 구분하는 레지스터가 있다. 따라서 이들 2칩을 구분하면 3개중 2개를 구분이 되니 W5100은 구분이 가능하다. 즉 W5200이 경우 version 레지스터(0x001F)를 읽으면 0x03이 읽히고, W5500의 경우 0x0039 번지를 읽으면 0x04가 읽힌다.

[table id=1 /]

### 아두이노 코드

아래 코드는 아두이노 Ethernet 코드를 수정하여 만든 코드이고, Webserver.ino에서 테스트를 했다.

관련 코드는 :<a href=" https://github.com/jbkim/Differentiate-WIznet-Chip" target="_blank"> https://github.com/jbkim/Differentiate-WIznet-Chip</a>