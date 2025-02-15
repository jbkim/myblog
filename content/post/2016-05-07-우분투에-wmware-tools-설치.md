---
title: 우분투에 WMware Tools 설치
author: openmicrolab
type: post
date: 2016-05-07T07:42:22+00:00
url: /우분투에-wmware-tools-설치/
categories:
  - 임베디드 리눅스
tags:
  - 우분투
  - WMware Tools
  - Ubuntu

---
만약 다음과 같은 메시지가 뜬다면 <a href="https://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=1017687" target="_blank">이 링크</a>의 내용을 참고 &#8211; 플로피 제거 및 CD/DVD를 삭제 및 다시 추가 후 진행

> VMware Tools installation cannot be started manually while Easy Install is in progress.

### 우분투에 WMware Tools 설치

Install WMware Tools 를 클릭하면 CD/DVD가 마운트 되됨는데, 여기에 있는 압축 파일을 copy후 풀어서 설치를 해야 한다.

> sudo mkdir /mnt/cdrom  
> sudo mount /dev/cdrom /mnt/cdrom/
> 
> cd /mnt/cdrom/  
> cp VMwareTools-9.6.1-1378637.tar.gz ~
> 
> cd ~  
> tar xvzf VMwareTools-9.6.1-1378637.tar.gz  
> cd vmware-tools-distrib/  
> sudo ./vmware-install.pl