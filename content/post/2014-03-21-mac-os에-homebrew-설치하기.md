---
title: MAC OS에 Homebrew 설치하기
author: openmicrolab
type: post
date: 2014-03-21T09:51:08+00:00
url: /mac-os에-homebrew-설치하기/
dsq_thread_id:
  - "2479847853"
categories:
  - Development
  - Tool
tags:
  - Mac OS X
  - Homebrew

---
OS X용 패키지 관리자인 Homebrew 설치하기  
영문 사이트:  <a href="http://brew.sh/" target="_blank">http://brew.sh/</a>  
한글 사이트: <a href="http://brew.sh/index_ko.html" target="_blank">http://brew.sh/index_ko.html</a>

설치는 간단하다. 터미널에서 다음을 실행한다.

<del><code id="selectable">&lt;strong>ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"&lt;/strong></code></del>  
위치가 바뀌어서 다음과 같이 입력을 해야 한다.  
<code id="selectable">ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"</code>  
다만 설치를 위해서는 Xcode용 Command Line Tools가 설치되어 있어야 한다.

### 주요 명령어

  * brew install formula // 패키지 설치
  * brew remove formula // 패키지 삭제
  * brew info formula // 패키지 정보
  * brew upgrade [formula] // 설치한 패키지의 최신버전을 설치
  * brew list 또는 brew ls // 설치한 formula 목록
  * brew update // Homebrew 업데이트
  * brew doctor // 시스템에 문제가 있는지 확인
  * brew outdated // 내가 설치한 formula 목록의 이후 버전이 나왔는지 확인
  * brew cleanup // fomula 의 모든 과거버전을 제거함