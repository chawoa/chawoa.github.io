---
title: 컴퓨터 네트워크 3 (Computer Networking)
date: 2024-09-27 00:00:40 +09:00
categories: [이론, 컴퓨터 네트워크]
tags: [컴퓨터 네트워크, Computer Networking]
mermaid: true
---

# 컴퓨터 네트워크 3 (Computer Networking)  

## 2장 목표  
   - Application-layer protocol  
      - 전송층 서비스 모델
      - 클라이언트-서버  
      - peer-to-peer  
      - 예시 : HTTP, SMTP, IMAP, DNS, video streaming  
      - 되면 socket 통신까지  

### 몇가지 네트워크 앱  
web, e-mail, 통신 게임, 저장된 스트리밍 비디오, IP를 통한 통화(EX. Skype), 실시간 비디오(저장된 것과 차이는 어디선가 사건이 일어나는 것을 즉각적으로 보는 것), 원격 로그인(EX. Anydesk)  

### 네트워크 앱의 생성  
모든 시스템은 end-system으로부터 네트워크를 통해 서로 통신한다.(EX. 웹서버, 브라우저) 여기서 core-network device란 라우팅이 가능한 라우터, 스위치등을 얘기한다. Access network device가 우리가 생각하는 서버, 핸드폰 등이다.  

### Client-server paradigm  
   - server  
      - 무언가를 제공하는 장치여야함.  
      - permanent IP address 영구적인 IP로 전세계 어디에서든 식별이 가능한 고유한 IP여야함.  
      - EX. data centers  
   - client  
      - 서버와 연결 통신하는 기기  
      - 주로 동적인 IP를 가짐  
      - 예전에는 클라이언트끼리 직접 통신이 불가했으나 지금은 가능  
      - EX. HTTP, IMAP, FTP  

### peer-peer  
두 가지 장치가 어느 서드 파티의 개입 없이 연결 및 통신 가능한 것이 p2p 통신이다. 직접적으로 서로 통신하며 파일을 주고 받는다. 요청을 보내 허가 후 이루어지지 않는 경우가 흔함. client server 통신의 경우 요청 수/송신 후 통신이 이루어짐.  

### process communicating  
프로세스란? 호스트 장치에서 돌아가는 프로그램들이다.  
같은 호스트내에서 두 개 프로세스가 inter-process communication을 통해 통신하는 것(EX. 네이버 창에 다른 회사의 광고)  
    - client server에서의 process  
      client process : 통신을 시작 시키는 프로세스  
      server process : 연결을 기다리는 프로세스  
  
*inter와 intra의 차이*  
- intra : 동일한 네트워크 내에서 서로 통신하는 것  
- inter : 다른 네트워크도 모두 사용하여서로 통신하는 것  

### Socket (주요 수단 중 하나 port Number)  
프로세스는 수/송신이 모두 가능하다. socket은 각 프로세스를 구별하기 위해서 존재한다. 모든 앱은 서로 다른 socket을 가진다. 메세지나 프로세스를 받기 위해서는 그들의 구별가능한 무언가가 있어야한다. (EX. 리액트의 3000번 포트) Socket이 필요한 이유는 하나의 장치에 IP가 할당되기 때문에 프로세스를 구별할 또다른 번호가 필요한 것이다. 만약 IP로 모든 프로세스를 다르게 할 수 있었다면 socket은 필요가 없었을 것이다. 포트와 IP를 통해서 각 서버의 모든 프로세스를 구별할 수 있는 것이다. 예를 들어 동일한 서비스를 사용하더라도 IP를 통해 호스트를 구별하고, 포트를 통해 요처 서비스를 구별한다.  

### 앱층의 프로토콜  
전 세계의 모든 사용자들이 어떠한 기준을 통해 통신할 수 있게 하기 위함이다. 보통은 각 지역에 특화되어 통신 환경이 구축되기 때문이다. 따라서 이러한 기준에 맞지 않으면 통신이 불가할 것이다.  
   - open protocol : 모든 사용자들이 사용하는 프로토콜(EX. HTTP, SMTP..)  
   - proprietary protocol : 기업과 같은 곳에서 사용하는 그들만의 프로토콜(EX. Kakao, skype..)

### 
   - data integrity : 몇 개의 앱들은 정확히 정보 및 데이터가 통신되어야한다는 100%의 신뢰성이 필요로 하며(EX. 파일 전송), 다른 앱들은 데이터 일부 손실에 대해 유연하다.(EX. 오디오, 비디오)  
   - timing : 몇 개의 앱들은 적절한 시간안에 통신이 이루어져야한다.(EX. 실시간 비디오, 실시간 상호작요 게임), 다른 앱들은 크게 필요하지 않을 수 있다.  
   - throughput : 몇 개의 앱들은 높은 처리율이 필요하다.(EX. 다운로드 파일), 다른 앱들은 크게 필요로 하지 않을 수 있다.(EX. email)  
   - security : 데이터의 암호화가 필요하며, 여기서 data integrity가 필요하다. 통신의 신뢰가 필요하기 때문이다.  

### TCP/UDP  
   - TCP    
      - reliable transport : TCP의 경우 데이터를 통신하기 전에 연결을 먼저 구성해야한다. 또한, 수신자 측에서도 송신자 측에 ACK를 통해 통신이 원활했다는 전송을 통해 신뢰성 있는 통신이 이루어진다.  
      - flow control : 대표적인 문제 bottle-neck를 해결하기 위함이다. 대역폭이 낮은 링크에 많은 데이터를 한번에 보내게되면 데이터 손실 일어난다. 따라서 그에 맞게 손실이 일어나지 않도록 데이터를 조절해서 전송하는 것이다.  
      - congestion control : 호스트와 라우터등의 처리 속도도 반영하는 넓은 의미의 제이이다.  

   - UDP  
      - unreliable data transfer : 연결을 형성하지 않고 데이터를 전송하기 때문에 신뢰성이 업다고 한다.  
      - 신뢰성, 흐름 제어, 혼잡 제어 등이 필요하지 않을 경우 UDP로 전송을 진행하게 된다.  

### Securing TCP  
   - Vanilla TCP & UDP socket : 암호화하지 않고, 통신하기 때문에 누구나 다 바로 확인 할 수 있다.  
   - TLS : 암호화된 상태로 모든 통신이 이루어지며, 호스트를 제외하고는 누구도 메세지를 수정할 수 없다. 단말기기에 로그인과 같은 인증 절차를 거치며 통신하는 것이다.  

### web & HTTP  
웹은 객체(EX. 그림, 링크..)의 구성이다. 다른 서버로부터 구성되는 객체도 구성 요소로 위치할 수 있다. 이런 모든 객체들은 각자의 url을 가지고 있으며, 이를 통해 웹에 나타난다.  
- HTTP의 과정  
   HTTP는 기본적으로 TCP를 사용하며, 보통 80번 포트를 사용한다. HTTP는 stateless인 상태로 과거의 정보를 저장하지 않는다. 과거의 상태를 지정하는 프로토콜의 경우 통신이 복잡해진다.  
   - Non-persistent HTTP : 통신을 할때마다 따로 요청을 보내야하기 때문에 매 전송 시 연결에 대한 요청이 이루어진다.  
   - Persistent HTTP : 여러개의 전송을 한번의 연결 요청으로 보낼 수 있다.  
- RTT : 수/송신자가 통신을 주고받는 한 번의 시간이다.  
   2개의 프로세스를 전송한다고 할 경우  
   - Non-persistent의 경우 4RTT(연결 요청, 파일 전송) + 파일 전송 시간  
   - Persistent의 경우 2번만 하면된다.  

- method  
   - POST : 사용자가 HTTP의 전체 body부분을 서버에 전송하는 것으로 보통 양식을 가진다.  
   - GET : 사용자 정보를 포함해서 GET요청을 보낸다.  
   - PUT : POST 안에 있는 객체 하나의 정보를 전송한다.  

Access란 권한을 통해 어떠한 것에 접근하거나 요청을 보낼 수 있는 것  
 