---
title: github에 SSH키 생성 및 등록
author: openmicrolab
type: post
date: 2015-01-31T11:13:44+00:00
url: /github에-ssh키-생성-및-등록/
categories:
  - Development
tags:
  - github
  - SSH
  - permission denied(publickey)
  - 깃헙

---
`Permission denied (publickey).<br />
fatal: Could not read from remote repository.`  
github을 잘 사용하다가 어느 순간 위와 같은 Permission 에러가 나서 다시 SSH키를 등록했다.

아래와 같이 터미널에 입력하는데 이메일은 github에 등록한 이메일을 사용한다.  
`ssh-keygen -t rsa -C “your_email@example.com”`

passphrase(암호)를 넣어준다.  
`Enter passphrase (empty for no passphrase):<br />
Enter same passphrase again:`

새로운 키를 에이전트에 추가한다.  
`eval “$(ssh-agent -s)”<br />
ssh-add ~/.ssh/id_rsa`

다음과 같이 입력하면 새로 만든 키가 클립보드에 저장이 된다.  
`pbcopy < ~/.ssh/id_rsa.pub`

github.com 에 로그인하고 Settings에 들어가 SSH Keys 메뉴를 선택하고, Add 버튼을 선택한 후 클립보드에 복사된 내용을 붙여 넣는다.

터미널에 입력하여 확인한다.  
`ssh -T git@github.com`

다음과 같은 메세지가 나타나면 정상  
`Hi username! You've successfully authenticated, but GitHub does not<br />
# provide shell access.`

참고: <a href="https://help.github.com/articles/generating-ssh-keys/" target="_blank">https://help.github.com/articles/generating-ssh-keys/</a>