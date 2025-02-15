---
title: 실내 측위 – BLE Tag, AoA, AoD
author: openmicrolab
type: post
date: 2018-04-21T10:27:27+00:00
url: /실내-측위-ble-tag-aoa-aod/
categories:
  - IoT
  - Wireless
  - Bluetooth
tags:
  - 실내 측위
  - BLE Tag
  - AoA
  - AoD

---
### 기존 비콘의 한계

  * Beacons only work with smartphones, not tags, which limits how they can be used
  * They are able to locate objects in best case within 3-4 meters, which is fine for determining a general location, but is not refined enough to meet the requirements for many of today’s applications
  * Beacons are battery-operated, which impacts their ability to deliver real-time location; frequent transmissions drain the device’s battery, meaning frequent replacements are necessary

### AoA, AoD의 사용

**AoA(신호의 수신 각도)**: 기기가 수신기 안테나 배열로 부터 오는 정확한 방향을 기반으로 한다. AoA를 사용하면 신호를 측정하기 위해 동일한 장치 내에서 여러 개의 안테나가 사용된다. 이렇게하면 안테나가 미터가 아닌 10-20 센티미터의 정확도로 태그 또는 스마트 폰을 찾을 수 있다.

**AoD (신호의 출발 각도)**: 이 접근법에서 위치 정보는 모바일 장치로 다시 이동한다. AoD 접근법은 &#8220;실내 GPS&#8221;와 같이 작동하는데 고정 인프라 장치 (Locators라고도 함)는 GPS 위성 작동 방식과 마찬가지로 수신 장치를 브로드캐스트하고 인식하지 못한다. 즉, 무제한의 장치를 찾을 수 있고 개인 정보 문제는 없다.

### <a href="https://www.iotcentral.io/blog/new-methods-drive-indoor-location-technologies-beyond-the-beacon" target="_blank" rel="noopener noreferrer">참고</a>