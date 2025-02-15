---
title: 삼성 Artik Edge-to-cloud Security
author: openmicrolab
type: post
date: 2017-11-14T09:22:28+00:00
url: /삼성-artik-edge-cloud-security/
categories:
  - IoT
  - Wireless
tags:
  - IOT
  - ARTIK
  - 보안
  - Edge-to-cloud Security
  - 삼성 아틱
  - 아틱
  - security

---
삼성 아틱의 보안은 Edge-to-cloud Security라고 설명을 한다. 즉 칩레벨에서 부터 클라우드까지 보안요소가 있다는 얘기.

### Device Protection and Trusted Code Execution

Hardware의 경우 Device protection과 trusted code execution이 가장 중심이 되는 요소임.

<img loading="lazy" class="" src="https://www.artik.io/wp-content/uploads/2017/10/device-protection-2-1024x469.png" width="703" height="322" /> 

  * **Secure Boot**  
    타겟 디바이스에서 동작하는 코드의 신뢰성을 보장이 필요  
    소프트웨어는 타겟장치에서 코드 실행을 허용하기 위해 소프트웨어 공급자가 서명해야함.
  * **KMS infrastructure for code signing**  
    코드 서명을 쉽게하기위한 Key Management Service (KMS), ARTIK CodeSigner service, FIPS-certified hardware security modules (HSM)를 제공
  * **Secure Element**  
    각 디바이스에 SmartThings cloud에 등록된 private/public key쌍이 저장이 되어서 출시됨.
  * **Secure JTAG access**  
    JTAG을 사용시 패스워드 필요

### Protected Communications

디바이스와 클라우드 사이의 통신 보안

<img loading="lazy" class="" src="https://www.artik.io/wp-content/uploads/2017/10/secure-comunication-2-1024x454.png" width="640" height="284" /> 

  * **Encryption**  
    <a href="https://lesstif.gitbooks.io/web-service-hardening/content/ssl-tls-https.html" target="_blank" rel="noopener noreferrer">Transport Layer Security (TLS)</a> 또는 datagram transport layer security (DTLS)사용  
    ARTIK modules also provide hardware acceleration (Crypto Engine) for AES and RSA encryption and decryption. Additionally, the ARTIK platform uses Elliptic Curve Diffie–Hellman (ECDH) for session encryption key generation, which provides a high level of protection with low power consumption.
  * **Authentication**  
    Public Key Infrastructure (PKI) 사용
  * **Easy secure onboarding**  
    Secure Device Registration (SDR): Mutual authentication between a gateway device and the cloud registration servers

### Edge-to-cloud Security

<img loading="lazy" class="" src="https://www.artik.io/wp-content/uploads/2017/10/security-overview-2-1024x417.png" width="690" height="281" />  
이 한장의 그림으로 지금까지 설명된 내용이 나와있음.

**참고**

  * <a href="https://www.artik.io/overview/samsung-artik-iot-security/device-protection/" target="_blank" rel="noopener noreferrer">https://www.artik.io/overview/samsung-artik-iot-security/device-protection/</a>
  * <a href="https://www.artik.io/overview/samsung-artik-iot-security/protected-communications/" target="_blank" rel="noopener noreferrer">https://www.artik.io/overview/samsung-artik-iot-security/protected-communications/</a>
  * <a href="https://www.artik.io/overview/samsung-artik-iot-security/edge-to-cloud-security/" target="_blank" rel="noopener noreferrer">https://www.artik.io/overview/samsung-artik-iot-security/edge-to-cloud-security/</a>