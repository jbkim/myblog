---
title: Google fit, Apple HealthKit으로 부터 Health data 가져오기
author: openmicrolab
type: post
date: 2022-11-09T07:54:21+00:00
url: /google-fit-apple-healthkit으로-부터-health-data-가져오기/
cloudinary_transformations_terms:
  - 'a:6:{i:0;s:12:"category:609";i:1;s:13:"post_tag:1322";i:2;s:13:"post_tag:1323";i:3;s:13:"post_tag:1324";i:4;s:13:"post_tag:1325";i:5;s:13:"post_tag:1326";}'
categories:
  - HealthCare
  - Development
tags:
  - Google Fit
  - HealthKit
  - Fitbit
  - STRAVA
  - healthcare

---
### Google Fit

[여기][1]에서 안드로이드 API나 REST API 관련 내용을 확인 가능

다음 4가지 데이터를 얻을 수 있음 (퍼미션 필요함)

  * Activity & Exercise — step count, burned calories, workout duration, basal metabolic rate, steep data.
  * Location — total running/cycling distance and speed as well as cycling cadence (RPM).
  * Body — heart rate, weight, body fat percentage.
  * Nutrition — food & hydration.

다음의 데이터는 OAuth가 필요함

  * Oxygen saturation
  * Body temperature
  * Blood pressure
  * Blood glucose
  * Cervical position and others

이런 데이터를 사용하는 것에 대한 [Term & Condition][2]

이중 몇가지 사항은  
&#8211; Google Fit API를 사용한다고 해서 앱이 자동으로 HIPAA를 준수하는 것은 아니다..  
&#8211; Google 피트니스에서 얻은 어떠한 콘텐츠도 판매하지 않으며 최종 사용자가 판매하도록 허용하지도 않는다.

### Apple’s HealthKit

Apple은 개발자가 사용할 수 있는 총 3개의 키트를 제공

  * HealthKit — 건강 및 피트니스 데이터 컨테이너. 다른 앱과의 원활한 통신을 가능하게 하고 건강 데이터를 쉽게 저장, 교환 및 수집할 수 있도록 한다.
  * ResearchKit — 이 프레임워크는 연구 목적으로 많은 사람들로부터 의료 데이터를 수집해야 하는 경우에 유용함
  * CareKit — 장기 및 만성 질환 모니터링 및 관리, 수술 후 회복 등을 위한 프레임워크
  * 애플이 구글보다 더 많은 데이터를 모으고 있는데 full list는 [여기][3]에서 확인 가능하다.
  * [Official pages of the iOS HealthKit framework][4]

### Garmin

  * [Garmin Health SDKs Overview][5]
  * [Garmin Health API Overview][6]

### Fitbit

  * [Fitbit SDK][7]
  * [Fitbit Web API][8]

### STRAVA

  * [개발자 사이트][9]

### Thryve

  * 찾아보니 애플, 구글, 삼성등의 디바이스로 부터 데이터를 가져와서 개발을 해주는 라는 회사가 있는데, &#8220;Get access to Thryve&#8217;s SDK and integrate 500+ wearables with your app&#8221; 이런 캐치프레이즈를 내걸고 있다.
  * <https://thryve.health/api-doc/index.php#introduction>

### 참고

  * <https://stormotion.io/blog/how-to-enable-google-fit-apple-healthkit-and-other-services-to-share-data-with-your-app>

 [1]: https://developers.google.com/fit/
 [2]: https://developers.google.com/fit/terms
 [3]: https://developer.apple.com/documentation/healthkit/data_types
 [4]: https://developer.apple.com/design/human-interface-guidelines/technologies/healthkit
 [5]: https://developer.garmin.com/health-sdk/overview/
 [6]: https://developer.garmin.com/gc-developer-program/health-api/
 [7]: https://dev.fitbit.com/getting-started/
 [8]: https://dev.fitbit.com/build/reference/web-api/developer-guide/application-design/
 [9]: https://developers.strava.com/