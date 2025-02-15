---
title: EAGLE 파일을 Fritzing 파일로 변환하기
author: openmicrolab
type: post
date: 2018-01-22T05:10:29+00:00
url: /eagle-파일을-fritzing-파일로-변환하기/
categories:
  - Uncategorized
tags:
  - Fritzing
  - Eagle
  - eagle2fritzing

---
####<img loading="lazy" class="alignnone wp-image-4197" src="https://res.cloudinary.com/openmicrolab/image/upload/v1516597806/eagle2fritzing_y1kj1g.png" width="690" height="278" /> 

#### 1. 아래 repo를 깃헙에서 클론한다.

<li style="font-weight: 400;">
  <span style="font-weight: 400;">Fritzing</span>
</li>

> <span style="font-weight: 400;">clone </span>[<span style="font-weight: 400;">https://github.com/fritzing/fritzing-app</span>][1]

  * Fritzing parts

> <a href="https://github.com/fritzing/fritzing-parts" target="_blank" rel="noopener noreferrer">https://github.com/fritzing/fritzing-parts</a>

<li style="font-weight: 400;">
  <span style="font-weight: 400;">eagle2fritzing </span>
</li>

> <span style="font-weight: 400;">clone </span>[<span style="font-weight: 400;">https://github.com/adafruit/eagle2fritzing</span>][2]

  * font download & install

> <http://fritzing.org/fritzings-graphic-standards/download-fonts-and-templates>

#### 2. eagle2fritzing의 brd2svg 빌드

  * 빌드시 xcode 9.2 가 필요하며, qt를 설치후 PATH 설정해야 한다.

> brew install qt  
> cd eagle2fritzing/brd2svg  
> qmake -spec macx-g++ brd2svg.pro  
> make

  * make를 하면 brd2svg가 빌드가 되는데,

> <span style="font-weight: 400;">clang: error: linker command failed with exit code 1 (use -v to see invocation)</span>

이런 에러가 발생하면, make파일에서 링크옵션에서 static을 제거하면 된다.

> LFLAGS = <del><strong>-static -static-libgcc -static-libstdc++</strong></del> -headerpad\_max\_install\_names $(EXPORT\_ARCH\_ARGS) -Wl,-syslibroot,/Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX10.13.sdk -mmacosx-version-min=10.10 -Wl,-rpath,@executable\_path/Frameworks

#### 3. 사용법

<li style="font-weight: 400;">
  <span style="font-weight: 400;">run.sh  파일을 수정한다.</span>
</li>
<li style="font-weight: 400;">
  <span style="font-weight: 400;">Eaglecad 위치설정</span>
</li>
<li style="font-weight: 400;">
  <span style="font-weight: 400;">WORKPATH 설정</span>
</li>
<li style="font-weight: 400;">
  <span style="font-weight: 400;">WORKPATH 아래 brds폴더를 만든후 여기에 board 파일을 위치시킨다. 즉 폴더의 구조는 다음과 같다.</span>
</li>

<span style="font-weight: 400;">     FOO</span><span style="font-weight: 400;"><br /> </span><span style="font-weight: 400;">     |&#8211; brds</span><span style="font-weight: 400;"><br /> </span><span style="font-weight: 400;">         |&#8211; board1.brd</span><span style="font-weight: 400;"><br /> </span><span style="font-weight: 400;">         |&#8211; board2.brd</span><span style="font-weight: 400;"><br /> </span><span style="font-weight: 400;">         |&#8211; board3.brd</span>

 [1]: https://github.com/fritzing/fritzing-app
 [2]: https://github.com/adafruit/eagle2fritzing