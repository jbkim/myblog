---
title: 이더넷 케이블 종류 – UTP, FTP, STP
author: openmicrolab
type: post
date: 2010-08-09T02:41:06+00:00
url: /이더넷-케이블-종류-utp-ftp-stp/
dsq_thread_id:
  - "1185526236"
categories:
  - Development
tags:
  - UTP
  - utp케이블
  - 랜선

---
UTP, FTP, STP케이블이 의미하는 바는 다음과 같다.

<img loading="lazy" src="/images/1/cfile1.uf.160407154C5F6A577B50AF.gif" class="aligncenter" width="600" height="309" alt="" filename="Cable.gif" filemime="image/jpeg" /> 

<span style="font-weight: bold;"><span style="font-size: 10pt;">UTP (Unshielded Twisted Pair)</span></span>  
쉴드가 없고 2선씩 쌍으로 꼬아져 있는 케이블  
2선씩 쌍으로 꼬아져 있는 이유는 이더넷 신호가 differential signal이기 때문에, 두 선간의 전자기 유도를 줄이기 위하여 서로 꼬여져있다. 제품 전선과 피복만으로 구성되어 있고, 일반적인 랜케이블에 해당됨.

<span style="font-weight: bold;"><span style="font-size: 10pt;">FTP(Foiled Twisted Pair)</span></span>  
쉴드 처리는 되어있지 않고, 알루미늄 은박이 4가닥의 선을 감싸고 있는 케이블.  
즉 UTP 케이블에 바깥쪽에 은박(foil)으로 감싸있는 케이블, Screended UTP (S/UTP) 라고도 함  
UTP에 비해 절연 기능이 탁월하므로 공장 배선용으로 많이 사용.

<span style="font-weight: bold;"><span style="font-size: 10pt;">STP (Shielded Twisted Pair)</span></span>  
2선씩 쌍으로 꼬아져 있는 케이블마다 쉴드가 있는 케이블, 여기에 바깥쪽에 은박이 하나더 있으면 S/STP라고 함.  
여기서 쉴드라 하는 것은 연선으로 된 케이블 겉에 외부 피복, 또는 차폐재가 추가되는데, 차폐재는 접지의 역할을 한다.&nbsp;  
따라서 외부의 노이즈를 차단하거나 전기적 신호의 간섭에 탁월한 성능이 있다.

따라서 외부 간섭에 가장 좋은 케이블 순서는 STP, FTP, UTP이다. 대부분의 경우 UTP를 사용하면 되며, 쉴드케이블의 경우 사용및 설치가 좀 복잡하다. 그리고 주의 할 점은 만약 제대로 쉴드가 그라운드 되지 않을 경우 아무런 장점이 없고 오히려 문제가 될수도 있다.

좀더 자세한 내용은 위키피디아에서.. <a title="[http://en.wikipedia.org/wiki/Twisted_pair]로 이동합니다." target="_blank" href="http://en.wikipedia.org/wiki/Twisted_pair">http://en.wikipedia.org/wiki/Twisted_pair</a>