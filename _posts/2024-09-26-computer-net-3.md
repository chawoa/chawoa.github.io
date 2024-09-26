---
title: 컴퓨터 네트워크 3 (Computer Networking)
date: 2024-09-26 13:00:40 +09:00
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



Access란 권한을 통해 어떠한 것에 접근하거나 요청을 보낼 수 있는 것  
 