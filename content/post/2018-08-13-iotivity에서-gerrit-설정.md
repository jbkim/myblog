---
title: Iotivity에서 gerrit 설정
author: openmicrolab
type: post
date: 2018-08-13T08:38:37+00:00
url: /iotivity에서-gerrit-설정/
categories:
  - IoT
tags:
  - IOT
  - Iotivity
  - gerrit

---
Iotivity에서 gerrit설정 및 git을 이용해 코드를 가져오는 방법

### Step 1: <a href="http://linuxfoundation.org" target="_blank" rel="noopener noreferrer">linuxfoundation.org</a> 에서 회원가입<span class="st0"><br /> </span> {#step_1create_ssh_keys}

### Step 2: Create SSH keys {#step_1create_ssh_keys}

<div class="level5">
  <pre class="code bash"><span class="co4">$ </span><span class="kw2">ssh-keygen</span> <span class="re5">-t</span> rsa <span class="re5">-C</span> <span class="st0">"Your name &lt;your_email_address&gt;"</span></pre>
  
  <p>
    ~/.ssh의 위치에 id_rsa와 id_rsa.pub가 생성이 된다. 참고로 맥에서 숨김 파일을 보려면 SHIFT + CMD + .
  </p>
</div>

### Step 3: Setting up SSH {#step_2setting_up_ssh}

<div class="level5">
  <p>
    ~/.ssh/config 파일을 다음과 같이 생성한다.
  </p>
  
  <pre class="code">Host gerrit.iotivity.org
    Hostname "gerrit.iotivity.org"
    IdentityFile ~/.ssh/id_rsa
    User &lt;Linux Foundation ID&gt;
    Port 29418</pre>
</div>

### Step 3: Upload SSH public key to Gerrit and Register personal info {#step_3upload_ssh_public_key_to_gerrit_and_register_personal_info}

<div class="level5">
  <p>
    <a class="urlextern" title="https://gerrit.iotivity.org/" href="https://gerrit.iotivity.org/" rel="nofollow">IoTivity Gerrit</a>에 로그인을 한후 Settings 메뉴에서 id_rsa.pub 파일의 내용 copy & paste 한다.
  </p>
  
  <p>
    <img loading="lazy" class="alignnone wp-image-4391" src="https://res.cloudinary.com/openmicrolab/image/upload/v1534149449/gerrit_gpenrd.png" width="575" height="192" />
  </p>
</div>

### Step 4: Verify your SSH connection {#step_4verify_your_ssh_connection}

<div class="level5">
  <pre class="code bash"><span class="co4">$ </span><span class="kw2">ssh</span> gerrit.iotivity.org</pre>
  
  <p>
    터미널에서 다음과 같은 메시지가 나오면 성공
  </p>
  
  <pre class="code">****    Welcome to Gerrit Code Review    ****</pre>
  
  <h3 id="step_4verify_your_ssh_connection">
    Step 5: Clone code
  </h3>
  
  <pre class="code bash"><span class="co4">$ git clone https://gerrit.iotivity.org/gerrit/iotivity
</span></pre>
  
  <pre class="code bash"><span class="co4">$ </span>cd iotIvity</pre>
  
  <pre class="code bash"><span class="co4">$ </span>git clone https://github.com/intel/tinycbor.git extlibs/tinycbor/tinycbor -b v0.5.1</pre>
  
  <pre class="code bash"><span class="co4">$ </span>git clone https://github.com/ARMmbed/mbedtls.git extlibs/mbedtls/mbedtls -b mbedtls-2.4.2</pre>
  
  <pre class="code bash"><span class="co4">$ </span>sudo apt-get install autoconf libtool doxygen valgrind wget unzip libboost-dev libboost-program-options-dev libboost-thread-dev uuid-dev libexpat1-dev libglib2.0-dev libsqlite3-dev libcurl4-gnutls-dev</pre>
  
  <p class="code bash">
    <span class="co4">$ </span>sudo apt-get install scons
  </p>
  
  <p>
    <strong>참고</strong> <a href="https://wiki.iotivity.org/how_to_use_gerrit" target="_blank" rel="noopener noreferrer">https://wiki.iotivity.org/how_to_use_gerrit</a>
  </p>
</div>