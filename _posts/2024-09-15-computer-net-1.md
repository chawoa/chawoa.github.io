---
title: 컴퓨터 네트워크 1 (Computer Networking)
date: 2024-09-15 00:00:40 +09:00
categories: [이론, 컴퓨터 네트워크]
tags: [컴퓨터 네트워크, Computer Networking]
mermaid: true
---

# 컴퓨터 네트워크 1 (Computer Networking)   

- ## **1징**   
   - ### **개요**   
      - *'Internet'이란 무엇인가?*   
      - *Network edge*   
      - *Network core*   
      - *Performance*   
      - *Protocol layers, service models*   
      - *Security*   
      - *History*   

   - ### **Internet에 대하여**   
      'Internet'과 'internet'의 차이는 'Internet'의 경우 WWW와 같이 연결되어있는 모든 네트워크를 뜻한다. 그에 반해 'internet'은 로컬 네트워크와 같은 작은 규모의 네트워크를 뜻한다.  
      네트워크에는 수십만개의 컴퓨팅 기기가 연결되어 있다. 각 단말기기를 우리는 hosts, end systems, consumer 라고 칭한다. 그러나 이런 기기들은 때에 따라 다를 수 있다. 예를 들어 지역 ISP가 국제 ISP로 부터 네트워크를 연결할 경우 지역 ISP는 Hosts이지만, 지역 ISP가 다른 기기에게 네트워크를 제공할 때는 Provider가 된다. 우리가 네트워크를 사용하는 모든 앱은 모두 edge에서 이루어진다는 것이다.   
      **네트워크 종류**   
      - Mobile network   
      - home network   
      - enterprise network   
      - content provider network(EX '데이터센터'지만 상황에 따라 provider network가 변화한다.)   


   - ### **프로토콜(protocols)**    
      프로토콜이란 task를 전송할때 지켜야할 규칙이다. 모든 컴퓨터 네트워킹은 프로토콜에 의해 관리된다. 프로토콜은 메세지의 통신 과정에서 형식과 순서를 정의한다. 또한, 이 프로토콜은 게이트웨이에서 변경될 수 있다.    
      만약 메세지 통신 과정에서 1, 2, 3의 전송을 거의 동시에 보냈을 때 2번 메세지가 정상적으로 전송되지 않았다면 송신자는 2번 메세지를 다시 보낸다. 그렇다면 수신자의 입장에서 1, 3, 2의 순서로 메세지가 도착했을 것이다. 이 경우 순서를 재정립한다.   
      프로토콜의 예로는 HTTP, streaming video(realtime, normal), Skype, TCP/IP, WIFI, 4G/5G, Ethernet(wired network)   
      
      - TCP / UDP의 차이 : 보안적인 측면으로 봤을 때 차이가 있다. TCP의 경우 연결을 위해 요청이 오고 가지만, UDP의 경우 해당 과정을 생략한다.   
      - 추가 정보   
         - Homogeneous Network : 모든 연결이 하나로만 이루어진 네트워크이다. (EX | WiFi로만, Ethernet으로만 등)   
         - Hedregeneous Network : 연결 종류가 2개 이상으로 이루어진 네트워크이다. (EX | 몇은 WiFi, 몇은 Ethernet 등)   

   - ### **표준**   
      ...   

   - ### **서비스 측면에서의 Internet**   
      - Infrastructure : 서비스를 앱에 제공하는 것 (EX | Web, email, games 등)   
      - programming interface : 앱에 기여하는 모든 것 (EX | API)   


   - ### **간단한 셀룰러 네트워크의 원리**   
      사용자가 근처의 BS(Base Station)으로 특정 대역폭을 활용하여 통신을 연결한다. 그럼 BS으로부터 Gateway를 통과하게되고 비로소 Internet으로 연결된다. 이러한 셀룰러 네트워크의 방식은 스마트폰 셀룰러 데이터, 자동차의 통신 등에서 사용된다. 그렇다면 와이파이를 사용하는 방법을 생각해보게 될 것이다. 그러나 와이파이는 셀룰러 네트워크 형식에 비해 범위가 작고 속도가 느리기 때문에 자동차와 같은 모빌리티에 적합하지 않다.   

   - ### **Network Edge**   
      - *Network Edge*   
         - hosts : 소비자와 서버(주로 데이터 센터)   
      - 




