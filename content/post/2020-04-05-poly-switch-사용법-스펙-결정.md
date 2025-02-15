---
title: Poly Switch 사용법 – 스펙 결정
author: openmicrolab
type: post
date: 2020-04-05T07:25:09+00:00
url: /poly-switch-사용법-스펙-결정/
categories:
  - Hardware
  - Infomation
  - Development
  - Semiconductor
tags:
  - PolySwitch
  - 과전류방지
  - 전원

---
### PolySwitch

회로에 과전류가 유입되면 열에 의하여 폴리스위치의 저항값이 커진다. 이에 따라 과전류를 제한하여 기기의 내부회로를 보호하게 된다. 반대로 소자의 온도가 낮아지게되면 저항값은 다시 초기상태로 돌아와 회로가 정상동작 하게 된다.

### 용어

  * Ih ( Hold Current ) : 최대 사용가능 전류  
    주위온도 20℃에서 이 전류값까지는 절대 동작(전류차단)하지 않으며, 정상적으로 동작하는 전류의 최대값을 말함.
  * It ( Trip Current ) : 최소 동작가능 전류  
    주위온도 20℃에서 이 전류값부터는 절대적으로 동작(전류차단)하며, 과전류로 판단할 수 있는 최소전류값을 말함

> 즉 Ih 부터 It사이에서 동작을 하는데, 얼마나 빠르게 퓨즈가 동작하는지 여부는 Time-to-Trip Graph를 참조해야 한다.

  * Vmax ( Maximum Device Voltage ) : 최대 사용가능 전압  
    이 전압값은 각 Part의 내전압을 의미하며 이 전압값이내에서는 각 Part의 사용이 가능
  * Imax ( Maximum Device Current ) : 최대 허용 전류  
    이 전류값은 각 Part의 내전류를 의미하며 이 전류값이내에서는 각 Part의 사용이 가능
  * Rmax ( Maximum Device Resistance ) : 최대 초기 저항치.
  * Rmin ( Minimum Device Resistance ) : 최소 초기 저항치.
  * R1max ( Minimum Device Resistance measured 1 hour post trip ) : Solder or 첫 Tirp후 1시간 이후의 최대 저항치

<div id="gtx-trans" style="position: absolute; left: -1px; top: 342.81px;">
  <div class="gtx-trans-icon">
  </div>
</div>