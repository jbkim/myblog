---
title: USB 디바이스의 VID, PID
author: openmicrolab
type: post
date: 2015-03-28T11:34:39+00:00
url: /usb-디바이스의-vid-pid/
featured_image: /wp-content/uploads/2014/03/800px-Arch_Pinout.jpg-100x100.png
categories:
  - Open Source Hardware
  - Infomation
  - Development
tags:
  - USB
  - VID
  - PID
  - openmoko

---
USB 디바이스 제품을 개발하려면 필요한 것이 USB 디바이스의 VID(Vendor ID), PID(Product ID)이다. 여기서 VID는 제조사의 ID이고, PID 제조사의 제품의 ID로 이해할 수 있는데 각각 2바이트로 VID-PID의 쌍으로 수많은 USB 디바이스와 구별이 가능하게 된다.  VID, PID는 USB Implementers Forum, Inc.(<a href="http://www.usb.org" target="_blank">http://www.usb.org</a>)에서 발급을 하는데 문제는 발급하는 데 드는 비용이 $5,000이다.

발급 신청서 링크 &#8211;<a href="%20http://www.usb.org/developers/vendor/VID_Only_Form_withCCAuth_010113.pdf" target="_blank"> http://www.usb.org/developers/vendor/VID_Only_Form_withCCAuth_010113.pdf</a>

이 발급 신청서에 보면 다음과 같이 발급된 VID는 다른 사람에게 판매할 수 없다고 되어 있다. 예외 조항은  &#8220;special circumstances, and then only upon prior written approval by USB-IF&#8221;

> The company set forth above hereby applies for a USB Vendor ID Number and agrees to the following: The USB Implementers Forum is the authority which assigns and maintains all USB Vendor ID Numbers. Each Vendor ID Number is assigned to one company for its sole and exclusive use, along with associated Product ID Numbers. They may not be sold, transferred, or used by others, directly or indirectly, except in special circumstances, and then only upon prior written approval by USB-IF. Unauthorized use of assigned or unassigned USB Vendor ID Numbers and associated Product ID Numbers are strictly prohibited.

하지만 MCS에서는 PID를 9.95유로에 판매(<a href="http://www.mcselec.com/index.php?page=shop.product_details&flypage=shop.flypage&product_id=92&option=com_phpshop&Itemid=1" target="_blank">링크</a>)를 한다. 그리고 <a href="http://wiki.openmoko.org/wiki/Main_Page" target="_blank">openmoko</a>의 경우 오픈소스하드웨어에 한하여 PID를 사용할 수 있게 하고 있다. <a href="http://wiki.openmoko.org/wiki/USB_Product_IDs" target="_blank">http://wiki.openmoko.org/wiki/USB_Product_IDs</a>  이 리스트를 보니, <a href="https://github.com/ErikZalm/Marlin" target="_blank">Marlin</a>, <a href="http://pinocc.io/" target="_blank">Pinoccio</a>, <a href="https://github.com/sprk/core" target="_blank">SparkCore</a>, <a href="http://tessel.io/" target="_blank">Tessel</a>등이 openmoko로 부터 PID를 받은 것을 알 수 있다.

<p class="p1">
  <span class="s1">각 업체들이 받은 VID, PID는 <a href="http://www.linux-usb.org/usb.ids" target="_blank">http://www.linux-usb.org/usb.ids</a>  링크를 참고. </span>그리고 PC에 연결된 디바이스의 VID, PID를 확인하려면 windows의 경우 장치관리자에서 확인이 가능하다.  <img loading="lazy" class="alignnone" src="http://openmicrolab.cdn2.cafe24.com/usb_pc.png" alt="" width="613" height="445" />
</p>

<p class="p1">
  Mac OS에서는 &#8220;이 Mac에 관하여 > 개요> 시스템 리포트의 USB&#8221; 항목에서 확인이 가능하다.
</p>

<img loading="lazy" class="alignnone" src="http://openmicrolab.cdn2.cafe24.com/USB_Mac.png" alt="" width="577" height="433" />