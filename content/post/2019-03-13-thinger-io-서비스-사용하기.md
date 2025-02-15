---
title: Thinger.io 서비스 사용하기
author: openmicrolab
type: post
date: 2019-03-13T08:48:49+00:00
url: /thinger-io-서비스-사용하기/
categories:
  - IoT
  - Wireless
  - Wi-Fi
tags:
  - IOT
  - ESP32
  - thinger.io

---
IoT 서비스 중 하나인 [Thinger.io][1]를 사용해 봤다.

아두이노 라이브러리를 제공을 해서 쉽게 ESP32에서 사용이 가능하다.

  * 먼저 아두이노 라이브러리 매니저에서 thinger로 검색을 해서 라이브러리를 설치를 하고 ESP32 예제를 연다.
  * 물론 먼저 이 서비스에 가입을 하고, USERNAME, DEVICE\_ID, DEVICE\_CREDENTIAL을 define 문에 정의한다.

> #define USERNAME “\***\***\***”
> 
> #define DEVICE_ID “\***\***\***”
> 
> #define DEVICE_CREDENTIAL “\***\***\***”

  * 접속하고자 하는 SSID와 SSID_PASSWORD를 입력한다.

> #define SSID “\***\***\***”  //your wifi SSID
> 
> #define SSID_PASSWORD “\***\***\***” // your wifi password

  * 아래 코드처럼 seup() 함수에 입출력을 정의하면, 서비스에서 이 값을 읽어서 대쉬보드에서 읽어서 데이터를 시각화 해준다.

> // digital pin control example (i.e. turning on/off a light, a relay, configuring a parameter, etc)
> 
> **thing[&#8220;BuiltInLed&#8221;] << digitalPin(2);**
> 
> // resource output example (i.e. reading a sensor value)
> 
> **thing\[&#8220;dht11&#8221;] >> [\](pson& out){**
> 
> **      out[&#8220;temperature&#8221;] = dht.readTemperature();**
> 
> **      out[&#8220;humidity&#8221;] = dht.readHumidity(); **
> 
> **}**

<img loading="lazy" class="alignnone wp-image-4559" src="https://res.cloudinary.com/openmicrolab/image/upload/v1552466828/thingerio_sx1h9c.png" width="719" height="616" /> 

> &nbsp;

 [1]: http://Thinger.io