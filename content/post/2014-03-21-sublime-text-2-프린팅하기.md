---
title: Sublime Text 2 프린팅하기
author: openmicrolab
type: post
date: 2014-03-21T10:06:44+00:00
url: /sublime-text-2-프린팅하기/
dsq_thread_id:
  - "2490695871"
categories:
  - Development
  - Tool
tags:
  - Sublime Text 2

---
Sublime Text 2에는 프린팅 기능이 없다. 플러그인을 설치를 해야하는데&#8230;

&#8220;Simple Print Function&#8221;를 인스톨한다.

> Tool > Command Palette > Install Package에서 &#8220;Simple Print Function&#8221;를 찾아서 인스톨한다.

이게 제대로 동작을 하려면 &#8220;enscript&#8221;가 필요하므로 brew를 사용하여 인스톨한다.

> brew install enscript

원래 소스 코드가 아닌 txt 파일을 인쇄하려고 했었는데, 프린트를 하면 한글은 깨짐. -_-;;;

참고로 Homebrew설치는 터미널에서 다음을 실행한다.

<code id="selectable">/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"</code>