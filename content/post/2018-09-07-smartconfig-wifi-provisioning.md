---
title: SmartConfig – WiFi provisioning
author: openmicrolab
type: post
date: 2018-09-07T09:34:48+00:00
url: /smartconfig-wifi-provisioning/
categories:
  - IoT
  - Wireless
  - Wi-Fi
tags:
  - WIFI
  - wi-fi
  - ESP8266
  - ESP32
  - smartconfig
  - wps
  - provisoning

---
유선 네트워크인 이더넷은 랜선을 연결하면 DHCP로 자동으로 IP가 부여된다. 하지만 WiFi에서는 AP의 이름 및 패스워드를 알고 AP에 접속을 해야지 IP를 얻을 수 있다. 이 과정이 WiFi provisoning인데, 스마트폰이나 PC와 달리 IoT 디바이스는 UI가 없는 경우가 많아서 AP의 이름이나 패스워드를 다른 방법으로 입력을 해야한다. 이때 주로 스마트폰을 사용을 하는데, 쉽게 말하면 스마트 폰을 이용해서 이 정보를 전달을 한다. 보통 디바이스를 softAP 모드로 놓고 이 디바이스에 스마트폰이 연결를 한후 UDP, TCP로 이 정보를 전달을 하는데, 이 방법외에 다음과 같은 방법이 있다.

### SamrtConfig

ESP8266, ESP32에서 사용하는 WiFi 설정프로그램은 TI사의 CC3000에서 사용했던 SmartConfig를 사용한다. 단말은 SmartConfig 모드(packet sniffing mode)에 있고 스마트 폰에서 SSID, PW를 암호화해서 UDP broadcasting한다. 단말은 이 패킷을 받아서 SSID에 접속을 하고 IP를 부여 받는다.

### WPS (WiFi Protected Setup)

WPS 버튼을 눌러서 기기를 세팅하는 방법. SSID, PW를 모르고 있어도 설정이 가능.

### Local AP

서두에 설명한대로 softAP로 동작을 하고 웹 또는 TCP, UDP로 SSID, PW를 전달하는 방식.

### 참고

  * <a href="http://depletionregion.blogspot.com/2013/10/cc3000-smart-config-transmitting-ssid.html" target="_blank" rel="noopener noreferrer">CC3000 Smart Config &#8211; transmitting SSID and keyphrase</a>
  * <a href="http://depletionregion.blogspot.com/2013/10/cc3000-smart-config-and-keyphrase.html" target="_blank" rel="noopener noreferrer">CC3000 Smart Config and keyphrase recovery</a>
  * <a href="http://depletionregion.blogspot.com/2013/10/cc3000-smart-config-and-aes.html" target="_blank" rel="noopener noreferrer">CC3000 Smart Config and AES</a>
  * <a href="http://www.switchdoc.com/2018/06/tutorial-esp32-bc24-provisioning-for-wifi/" target="_blank" rel="noopener noreferrer">Tutorial: Provisioning your ESP32 for WiFi. 3 Different Ways.</a>