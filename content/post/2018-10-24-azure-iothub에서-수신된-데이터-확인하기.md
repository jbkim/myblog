---
title: Azure IoThub에서 수신된 데이터 확인하기
author: openmicrolab
type: post
date: 2018-10-24T09:41:51+00:00
url: /azure-iothub에서-수신된-데이터-확인하기/
categories:
  - IoT
  - Wireless
  - Wi-Fi
tags:
  - IOT
  - Azure
  - Azure IoThub

---
Azure IoThub에 디바이스를 연결하고 MQTT 프로토콜을 이용해서 데이터를 보내면 이 내용을 Monitoring > Metric 에서 설정하는 대로 그래프로 표시된다. 하지만 메시지 포멧과 데이터의 값을 보려면 콘솔을 열고 다음과 같은 명령을 입력해야 한다.

> az iot hub monitor-events &#8211;hub-name {IotHub Name} &#8211;output table

여기서 IotHub Name는 생성한 IoTHub의 이름이다.

<img loading="lazy" class="alignnone wp-image-4447" src="https://res.cloudinary.com/openmicrolab/image/upload/v1540374019/azure_Iothub_pwlwda.png" width="839" height="479" /> 

위 내용은 작년(2018)에 테스트를 하던 건데 오늘(2019.5.2) 다시 테스트를 하려고 보니 안된다. 구글링 해보니 CLI 명령어가 바뀜. 이 [링크][1] 를 확인.

> az iot hub monitor-events -n {iothub_name}

 [1]: https://docs.microsoft.com/en-us/cli/azure/ext/azure-cli-iot-ext/iot/hub?view=azure-cli-latest#ext-azure-cli-iot-ext-az-iot-hub-monitor-events