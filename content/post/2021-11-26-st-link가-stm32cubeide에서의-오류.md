---
title: ST-LINK가 STM32CubeIDE에서의 오류
author: openmicrolab
type: post
date: 2021-11-26T01:42:32+00:00
url: /st-link가-stm32cubeide에서의-오류/
cloudinary_transformations_terms:
  - 'a:6:{i:0;s:12:"category:650";i:1;s:12:"category:609";i:2;s:12:"category:627";i:3;s:12:"post_tag:177";i:4;s:13:"post_tag:1222";i:5;s:13:"post_tag:1319";}'
categories:
  - ARM
  - Infomation
  - Development
tags:
  - STM32
  - ST-LINK
  - stm32cubeIDE

---
기존에 사용하던 ST-LINK가 있었고, 새로 구매한 ST-LINK를 연결해서 테스트를 하려고 했는데, 다음과 같은 에러 메시지가 보인다. ST-LINK의 펌웨어도 업데이트를 해보았으나 동일한 메시지가 계속 발생.

[<img loading="lazy" class="aligncenter  wp-image-4808" src="/images/2021/11/st-link1.png" alt="" width="471" height="114" srcset="/images/2021/11/st-link1.png 578w, /images/2021/11/st-link1-300x73.png 300w" sizes="(max-width: 471px) 100vw, 471px" />][1]

디버그 설정에서 보니 ST-LINK S/N 에서 Scan을 하면 자동으로 리스트가 업데이트가 되는 것이 아니라, **리스트 중에 하나를 수동으로 선택 해야하는 것.**

[<img loading="lazy" class="aligncenter  wp-image-4809" src="/images/2021/11/stm32cubeIDE.png" alt="" width="574" height="527" srcset="/images/2021/11/stm32cubeIDE.png 803w, /images/2021/11/stm32cubeIDE-300x275.png 300w, /images/2021/11/stm32cubeIDE-768x705.png 768w" sizes="(max-width: 574px) 100vw, 574px" />][2]

 [1]: /images/2021/11/st-link1.png
 [2]: /images/2021/11/stm32cubeIDE.png