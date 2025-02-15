---
title: Anaconda를 사용하여 Tensorflow 설치
author: openmicrolab
type: post
date: 2021-01-30T05:05:14+00:00
url: /anaconda를-사용하여-tensorflow-설치/
categories:
  - Machine learning
tags:
  - tensorflow

---
$ conda upgrade pip  
$ pip install upgrade

// 가상환경 만들기 (tensoflow 2.4 버전에서는 python 3.8을 사용함)  
$ conda create -n tf14 python=3.6

// 가상환경 활성화  
$ conda activate tf14  
(tf14) pip install tensorflow==1.14.0

// Tensorflow 설치  
(tf14) pip install &#8211;ignore-installed &#8211;upgrade tensorflow-cpu

// TF lite 코드 다운로드 (github CLI를 설치했음)  
(tf14) gh repo clone tensorflow/tensorflow

// Hello World 예제의 테스트 빌드로 확인  
$ make -f tensorflow/lite/micro/tools/make/Makefile test\_hello\_world_test