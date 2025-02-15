---
title: Xcode, Pip, Virtualenv, VirtualenvWrapper 설치하기
author: openmicrolab
type: post
date: 2014-08-20T02:39:34+00:00
url: /xcode-pip-virtualenv-virtualenvwrapper-설치하기/
dsq_thread_id:
  - "2949370466"
categories:
  - Development
  - Tool
tags:
  - Python deplyment
  - Pip
  - Virtualenv
  - VirtualenvWrapper

---
### Xcode

Xcode와 Xcode command line tool은 Mac에서 개발을 하려면 필요한 툴.  App Store에서 다운로드해서 설치한다. Xcode의 설치여부를 확인하는 방법

<pre>$ xcode-select -p</pre>

설치가 되어있으면  다음과 같이 표시가 된다.

<pre>/Applications/Xcode.app/Contents/Developer</pre>

Command line tool은 다음과 같이 해서 설치를 하는데,  /Library/Developer/CommandLineTool/ 위치에 설치가 된다.

<pre>xcode-select —install
</pre>

gcc의 버젼 확인

<pre>$ gcc --version
Python deployment를 위한 툴인 pip, virtualenv, virtualwrapper의 설치</pre>

### <a href="https://pypi.python.org/pypi/pip" target="_blank">Pip</a>

<pre>sudo easy_install pip</pre>

### <a href="https://pypi.python.org/pypi/virtualenv" target="_blank">Vitualenv</a>

<pre>sudo pip install virtualenv</pre>

### <a href="https://bitbucket.org/dhellmann/virtualenvwrapper" target="_blank">VitualenvWrapper</a>

<pre>sudo pip install virtualenvwrapper</pre>

.virtualenvs 폴더를 만든다.

<pre>cd $HOME
mkdir .virtualenvs</pre>

Shell이 virtualenvwrapper.sh를 로드하도록 하기 위해 다음과 같이 작업

<pre>vi .bash_login</pre>

다음 내용을 적고 저장.

<pre>source /usr/local/bin/virtualenvwrapper.sh</pre>