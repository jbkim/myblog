---
title: Simplicity Studio 5 – 맥에서 이슈 해결
author: openmicrolab
type: post
date: 2021-05-20T02:52:19+00:00
url: /simplicity-studio-5-맥에서-이슈-해결/
cloudinary_transformations_terms:
  - 'a:3:{i:0;s:12:"category:286";i:1;s:13:"category:1028";i:2;s:13:"post_tag:1132";}'
categories:
  - Wireless
  - Bluetooth
tags:
  - Silab

---
Silab 사의 개발 환경인 Simplicity Studio 5 를 맥(Big Sur)에서 사용시 프로젝트를 구성을 할 때 Bluetooth Configurator 가 제대로 안되고 에러가 난다.

> _An internal error occurred during: &#8220;Generating apack_btConfig for **project_name**&#8220;._
> 
> _Failed to generate setup apack_btConfig exited with 134:_
> 
> _dyld: Library not loaded: /System/Library/Frameworks/CoreFoundation.framework/Versions/A/CoreFoundation_
> 
> _  Referenced from: /Applications/Simplicity Studio.app/Contents/Eclipse/developer/adapter_packs/python/bin/python3_
> 
> _  Reason: image not found_

문제를 해결하기 위해서는 _/Applications/Simplicity Studio.app/Contents/Eclipse/developer/adapter_packs/python/bin/_ 이 위치에 설치된 파이썬을 사용하지 않고 Python 3.6버전을 사용하고 이 버전에 심볼릭 링크를 거는 것이다.

> **1.  Create a python 3.6 anaconda environment. Activate it and find the location of python in the env.**
> 
> In my case, it is /Users/user_name/opt/anaconda3/envs/studio/bin/python
> 
> **2. Soft link all python files to that location in the following location.**  
> /Applications/Simplicity Studio.app/Contents/Eclipse/developer/adapter_packs/python/bin
> 
> ln -s /Users/yaoyu/opt/anaconda3/envs/studio/bin/python ./python
> 
> ln -s /Users/yaoyu/opt/anaconda3/envs/studio/bin/python ./python3
> 
> ln -s /Users/yaoyu/opt/anaconda3/envs/studio/bin/python ./python3.6

참고: [https://www.silabs.com/community/software/simplicity-studio/forum.topic.topic.15.15.html/macos\_big\_sur_support-UO87 ][1]

&nbsp;

 [1]: https://www.silabs.com/community/software/simplicity-studio/forum.topic.topic.15.15.html/macos_big_sur_support-UO87