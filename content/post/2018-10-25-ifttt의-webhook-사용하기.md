---
title: IFTTT의 Webhook 사용하기
author: openmicrolab
type: post
date: 2018-10-25T10:12:42+00:00
url: /ifttt의-webhook-사용하기/
categories:
  - IoT
tags:
  - IOT
  - IFTTT
  - Webhook

---
IFTTT에서 Webhook 서비스를 만들고 이 서비스의 endpoint 를 찾을 수가 없었는데, 이것은 <a href="https://ifttt.com/services/maker_webhooks/settings" target="_blank" rel="noopener noreferrer">https://ifttt.com/services/maker_webhooks/settings</a> 에서 찾을 수 있다.

이 페이지에서 나온 URL을 브라우저에 입력을 하면 키값과 POST GET을 할 수 있는 URL 정보를 얻을 수 있다. 여기서 {event}의 값은 생성한 서비스의 event 이름이다.

> https://maker.ifttt.com/trigger/{event}}/with/key/{key 값}

<img loading="lazy" class="alignnone wp-image-4461" src="https://res.cloudinary.com/openmicrolab/image/upload/v1540461977/ifttt_kgy2ad.png" width="759" height="426" /> 

IF + Webhook + Notification 으로 만들면 IFTTT앱에서 알림을 받을 수 있다.

**참고**

<a href="https://help.ifttt.com/hc/en-us/articles/115010230347-The-Webhooks-Service" target="_blank" rel="noopener noreferrer">https://help.ifttt.com/hc/en-us/articles/115010230347-The-Webhooks-Service</a>

<blockquote class="wp-embedded-content" data-secret="Rf5yuLTtD7">
  <p>
    <a href="https://www.learnrobotics.org/blog/connect-arduino-to-ifttt-for-iot-projects/">Connect Arduino to IFTTT for IoT Projects</a>
  </p>
</blockquote>