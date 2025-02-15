---
title: nRF52 Segger Embedded Studio 설정 – CMSIS Configuration Wizard
author: openmicrolab
type: post
date: 2021-09-03T05:58:01+00:00
url: /nrf52-segger-embedded-studio-설정-cmsis-configuration-wizard/
cloudinary_transformations_terms:
  - 'a:8:{i:0;s:12:"category:660";i:1;s:13:"category:1028";i:2;s:12:"category:609";i:3;s:12:"category:627";i:4;s:13:"post_tag:1314";i:5;s:13:"post_tag:1300";i:6;s:13:"post_tag:1315";i:7;s:13:"post_tag:1316";}'
categories:
  - IoT
  - Bluetooth
  - Infomation
  - Development
tags:
  - SES
  - nrf52840
  - Segger Embedded Studio
  - CMSIS Configuration Wizard

---
노르딕에서 제공하는 예제코드의 경우 SDK 설정이 sdk_config.h에서 이루어 진다. 문제는 이 파일의 사이즈가 크고 #ifdef 등으로 설정이 되어 있어서 파일 자체를 보기가 불편하다. 그래서 이 설정을 쉽게 하는 툴이 제공이 되는데, 기본 SES 설정에는 없어서 따로 설정을 해야 한다.

<ol type="1">
  <li>
    Go to <b>File -> Open Studio Folder&#8230; -> External Tools Configuration</b>.
  </li>
  <li>
    The tools.xml file will be opened in the editor. <div class="fragment">
    </div>
  </li>
</ol>

다음의 코드를 삽입한다

<div class="line">
  <item name=<span class="stringliteral">&#8220;Tool.CMSIS_Config_Wizard&#8221;</span> wait=<span class="stringliteral">&#8220;no&#8221;</span>>
</div>

<div class="line">
       <menu>&CMSIS Configuration Wizard</menu>
</div>

<div class="line">
       <text>CMSIS Configuration Wizard</text>
</div>

<div class="line">
       <tip>Open a configuration file in CMSIS Configuration Wizard</tip>
</div>

<div class="line">
       <key>Ctrl+Y</key>
</div>

<div class="line">
       <match>*config*.h</match>
</div>

<div class="line">
       <message>CMSIS Config</message>
</div>

<div class="line">
       <commands>
</div>

<div class="line">
           java -jar &quot;$(CMSIS_CONFIG_TOOL)&quot; &quot;$(InputPath)&quot;
</div>

<div class="line">
       </commands>
</div>

<div>
  </item>
</div>

참고 &#8211; <a href="https://infocenter.nordicsemi.com/index.jsp?topic=%2Fcom.nordic.infocenter.sdk5.v15.0.0%2Fsdk_config.html" target="_blank" rel="noopener">https://infocenter.nordicsemi.com/index.jsp?topic=%2Fcom.nordic.infocenter.sdk5.v15.0.0%2Fsdk_config.html</a>