---
title: 'BLE over UART  throughput'
author: openmicrolab
type: post
date: 2021-09-24T05:41:27+00:00
url: /ble-over-uart-throughput/
cloudinary_transformations_terms:
  - 'a:3:{i:0;s:13:"category:1028";i:1;s:13:"post_tag:1284";i:2;s:13:"post_tag:1318";}'
categories:
  - Bluetooth
tags:
  - nrf
  - BLE 성능

---
Adafruit사의 <a href="https://learn.adafruit.com/adafruit-feather-m0-bluefruit-le?view=all" target="_blank" rel="noopener">Feather m0 bluefruit</a> 보드의 UART to BLE Throughput 측정. PC측에는 nRF Connect 앱인 BLE 앱을 사용함.

[<img loading="lazy" class="aligncenter  wp-image-4803" src="/images/2021/09/nRF_BLE-300x232.png" alt="" width="417" height="323" srcset="/images/2021/09/nRF_BLE-300x232.png 300w, /images/2021/09/nRF_BLE-1024x791.png 1024w, /images/2021/09/nRF_BLE-768x593.png 768w, /images/2021/09/nRF_BLE.png 1032w" sizes="(max-width: 417px) 100vw, 417px" />][1]

이 앱에서 연결을 하고 데이터를 수신한다. 보내는 측의 로그를 확인하면 대략 4.71KB/S 정도 나오는데, 핸드폰 앱에서 확인해보니 4KB/S 정도 나옴.

[<img loading="lazy" class="aligncenter size-medium wp-image-4802" src="/images/2021/09/Ble_ThroughtPut-300x221.png" alt="" width="300" height="221" srcset="/images/2021/09/Ble_ThroughtPut-300x221.png 300w, /images/2021/09/Ble_ThroughtPut.png 368w" sizes="(max-width: 300px) 100vw, 300px" />][2]

성능도 중요하지만 무선이므로 데이터 손실이 없을 수 없으며, 찾아보니 그 이유중 하나는 다음과 같다. (출처 &#8211; <a href="https://interrupt.memfault.com/blog/ble-throughput-primer" target="_blank" rel="noopener">https://interrupt.memfault.com/blog/ble-throughput-primer</a>)

> Counterintuitively, even though the Link Layer of BLE is <i data-stringify-type="italic">reliable</i>, packet loss is still something to be concerned about for BLE. This is because many many stacks drop data within the software stack. For example, BLE messages get queued up in the stack and when the heap holding the packets runs out of memory, some stacks will silently drop data. This means if you are sending large amounts of data over BLE you will usually want to add some sort of reliability layer that can detect & retransmit messages when data is dropped. The way this is implemented can have sizeable impacts on throughput. For example, if you have designed your own protocol on top of L2CAP or GATT and every message sent requires an acknowledgement before another message is sent, you’ll typically wind up adding a connection interval worth of latency getting the data sent out, effectively halving the max throughput which can be achieved.

즉 BLE Link Layer는 reliable하지만 BLE stack에서 힙의 메모리가 부족할 때 일부 스택은 자동으로 데이터를 삭제된다. 따라서 상위레벨의 프로토콜에서 재전송 기법을 사용해야 함.

<a href="https://www.mdpi.com/2079-6374/11/10/350" target="_blank" rel="noopener">Mitigation of Data Packet Loss in Bluetooth Low Energy-Based Wearable Healthcare Ecosystem</a> 이 문서의 내용 참고

&nbsp;

 [1]: /images/2021/09/nRF_BLE.png
 [2]: /images/2021/09/Ble_ThroughtPut.png