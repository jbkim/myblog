---
title: Intel Galileo board와 Arduino Tre
author: openmicrolab
type: post
date: 2013-10-07T08:08:37+00:00
url: /intel-galileo-board와-arduino-tre/
dsq_thread_id:
  - "1834469343"
categories:
  - Open Source Hardware
tags:
  - Arduino
  - Open source hardware
  - Intel Galileo board
  - Arduino Tre
  - Arduino Certified
  - Arduino at Heart

---
### Intel Galileo Board

최근 <a href="http://arduino.cc/" target="_blank">아두이노</a>는 매년 메이커페어에서 신제품의 출시에 대한 내용을 발표하는 것 같다. 올해는 지난 주말에 이태리 로마에서 있었던 <a href="http://www.makerfairerome.eu/en/" target="_blank">메이커페어 유럽에디션</a>에서 인텔과의 협력으로 나온 보드인 <a href="http://arduino.cc/en/ArduinoCertified/IntelGalileo" target="_blank">Intel Galileo Board</a>를 발표를 했다. PC 기반의 칩셋업체인 인텔이 임베디드분야에 그것도 오픈하드웨어에 발을 담그기 시작한 것이니 최근 오픈 소스 하드웨어의 열풍이 세상을 변화시키고 있는 것은 확실한 것 같다.

> 그런데 한가지 재미있는 것은 이 제품이 아두이노의 &#8220;Arduino Certified&#8221; 제품군에 들어간 것이다. 우리가 익히 알고 있듯이 인텔은 자신들의 칩셋을 PC 업체에 공급을 하면서 Intel Inside라는 로고를 붙이게 했다. 하지만 오픈소스하드웨어 시장에서는 도리어 아두이노가 거대 기업 인텔에게 &#8220;Arduino Certified&#8221;라는 로고를 주다니&#8230;

### <a href="http://arduino.cc/en/ArduinoCertified/Products" target="_blank">Arduino Certified</a> & <a href="http://arduino.cc/en/ArduinoAtHeart/HomePage" target="_blank">Arduino at Heart</a> Program

아두이노가 유명세를 타면서 많은 클론과 카피켓들이 나오고 있는 상황에서 &#8220;Arduino Certified&#8221;는 이에 대한 대안으로 생각이 된다. 이제 시장에서 &#8220;Arduino Certified&#8221;가 붙지 않은 제품들은 아무래도 입지가 좁아들 것이고, 반대로 아두이노는 더 큰 영향력을 갖게 될 것이다.

[<img loading="lazy" class="alignnone size-full wp-image-2852" alt="ArduinoAtHeart_logo" src="/images/2013/10/ArduinoAtHeart_logo.png" width="554" height="136" srcset="/images/2013/10/ArduinoAtHeart_logo.png 554w, /images/2013/10/ArduinoAtHeart_logo-300x73.png 300w" sizes="(max-width: 554px) 100vw, 554px" />][1]

이것과 함께, <a href="http://arduino.cc/en/ArduinoAtHeart/HomePage" target="_blank">Arduino at Heart Program</a>이 소개가 되었는데, 이것은 Atmel 칩을 사용하면서 아두이노 플랫폼에 기반한 제품들에 주는 로고이다. 즉 아래 칩들을 사용한 제품이 아두이노 기반의 코드로 만들어 있다면 <a href="http://arduino.cc/en/ArduinoAtHeart/HomePage" target="_blank">Arduino at Heart</a> 로고를 준다. 아마도 이것은 Atmel과 같이 기획한 냄새가 많이 나는데, 오픈소스하드웨어가 기존의 프로토타입이나 하비스트의 제품을 넘어서 완제품까지 연결이 되는 시대가 왔음을 시사하는 것 같다.

  * ATMega328 clocked at 8 or 16 MHz
  * ATMega1280 clocked at 16 MHz
  * ATMega2560 clocked at 16 MHz
  * ATMega32U4 clocked at 16MHz
  * SAM3X

이 프로그램의 혜택은 아두이노 커뮤니티의 도움을 얻을 수 있고, 사용자가 커스터마이징이 가능하며, 아두이노 채널(홈페이지, 트위터 및 기타 마케팅 채널)을 통해서 프로모션을 해준다는 것. 물론 이 로고를 붙이기 위한 라이센스 비용이 필요하다. -_-;;

<div style="width: 624px" class="wp-caption alignnone">
  <img loading="lazy" class=" " alt="" src="http://arduino.cc/en/uploads/ArduinoCertified/IntelGalileo_fabD_Front.jpg" width="614" height="463" />
  
  <p class="wp-caption-text">
    Intel® Quark SoC X1000 Application Processor
  </p>
</div>

아무튼 보드의 스펙을 보면 펜티엄기반 Intel® Quark SoC X1000 Application Processor를 사용하고, 아두이노의 IDE 를 사용해서 프로그래밍이 가능하다. 물론 기존의 쉴드들도 사용이 가능하다고 한다.

관련기사: <a href="http://blog.arduino.cc/2013/10/03/massimo-banzi-reveals-an-exciting-new-product-and-collaboration-with-intel/" target="_blank">http://blog.arduino.cc/2013/10/03/massimo-banzi-reveals-an-exciting-new-product-and-collaboration-with-intel/</a>

개봉기: <a href="http://www.flickr.com/photos/brucesterling/sets/72157636182707015/" target="_blank">http://www.flickr.com/photos/brucesterling/sets/72157636182707015/</a>

### <a href="http://arduino.cc/en/Main/ArduinoBoardTre" target="_blank">Arduino Tre</a>

<div style="width: 490px" class="wp-caption alignnone">
  <img loading="lazy" class=" " alt="" src="http://arduino.cc/en/uploads/Main/ArduinoTre_LandingPage.jpg" width="480" height="327" />
  
  <p class="wp-caption-text">
    Arduino Tre
  </p>
</div>

Tre는 이태리어로 3이라는 뜻인데, 기존 Uno, Due보드의 후속의 성격이다. 하지만 TI의 1-GHz Sitara AM335x을 사용해 우노나 네오나르도 보드보다 100배 빠르다고 한다. <a href="http://arduino.cc/en/Main/ArduinoBoardYun" target="_blank">Arduino Yun보드</a>가 리눅스를 사용한 것 처럼 이보드 역시 리눅스 기반인데 더 의미가 있는 것은 <a href="http://beagleboard.org/blog/2013-10-03-beagleboardorg-collaborates-with-arduino/" target="_blank">Beagleboard</a>와 협력해서 나온 작품이라는 것이다.

> 즉 Beaglbone Black에 사용된 동일한 칩을 사용하고 있다. 인텔과의 콜레보레이션에 이어 TI와 콜레보레이션 이라&#8230; 아두이노는 8비트 기반에서 High-end로 가고 싶었고, BeagleBoard는 아두이노의 다양한 쉴드 및 커뮤니티를 원했던 것이 아닌가 생각이 된다. ^^*

관련기사: <a href="http://beagleboard.org/blog/2013-10-03-beagleboardorg-collaborates-with-arduino/" target="_blank">http://beagleboard.org/blog/2013-10-03-beagleboardorg-collaborates-with-arduino/</a>

 [1]: /images/2013/10/ArduinoAtHeart_logo.png