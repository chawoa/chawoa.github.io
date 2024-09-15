---
title: 컴퓨터 네트워크 1 (Computer Networking)
date: 2024-09-15 00:00:40 +09:00
categories: [이론, 컴퓨터 네트워크]
tags: [컴퓨터 네트워크, Computer Networking]
mermaid: true
---

# 컴퓨터 네트워크 1 (Computer Networking)   

- ## **1장**   
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
         Homogeneous Network : 모든 연결이 하나로만 이루어진 네트워크이다. (EX WiFi로만, Ethernet으로만 등)   
         Hedregeneous Network : 연결 종류가 2개 이상으로 이루어진 네트워크이다. (EX 몇은 WiFi, 몇은 Ethernet 등)   

   - ### **표준**   
      ...   

   - ### **서비스 측면에서의 Internet**   
      Infrastructure : 서비스를 앱에 제공하는 것 (EX Web, email, games 등)   
      programming interface : 앱에 기여하는 모든 것 (EX API)   


   - ### **간단한 셀룰러 네트워크의 원리**   
      사용자가 근처의 BS(Base Station)으로 특정 대역폭을 활용하여 통신을 연결한다. 그럼 BS으로부터 Gateway를 통과하게되고 비로소 Internet으로 연결된다. 이러한 셀룰러 네트워크의 방식은 스마트폰 셀룰러 데이터, 자동차의 통신 등에서 사용된다. 그렇다면 와이파이를 사용하는 방법을 생각해보게 될 것이다. 그러나 와이파이는 셀룰러 네트워크 형식에 비해 범위가 작고 속도가 느리기 때문에 자동차와 같은 모빌리티에 적합하지 않다.   

   - ### **Network Edge**   
      - *Host&Links*   
         - hosts : 소비자와 서버(주로 데이터 센터), Application으로 부터 메세지를 만들어 더 작은 단위인 L 비트의 패킷들로 생성한다. 해당 패킷 전송 과정에서 사용되는 링크의 대역폭에 따라 전송률이 달라진다. 예를 들면 다음과 같다.   
            
         링크 전송률 : 링크가 담을 수 있는 패킷의 양. 즉, 링크의 대역폭   
         패킷 전송 지연율 : L bits / 링크 전송률(bits/sec)   
            
         - links   
            - TP (Twisted pair) : 보통 알고있는 랜케이블이 예시이다.   
            - Coaxial cable (동축 케이블) : 양방향 통신(bidirectional)을 하고? ...   
            - Fiber optic cable (광케이블) : 가장 빠른 전송률을 가지고 있으며, 빛 반사를 사용한 통신을 하기 때문에 빛 흡수가 나타나지 않으면 감쇄가 잘 일어나지 않는다. 따라서 전송 중간에 증폭기(repeater)가 많이 필요하지 않고, 전기적 간섭에도 안정적이므로 통신 장애가 드물다. 단 한가지 단점이라면 비용적인 부분이다.   
      - *Access network* : Network core로부터 네트워크 서비스를 받는 네트워크이다. (EX BS, Access Point 등)   
         - Cable-based access   
            - FDM (Frequency division multiplexing)   
               각 대역폭을 구분하여 전송하는 방법이다. 시간에 관계없이 대역폭을 각자 나누어 사용이 가능하다.   
            - TDM (Time division multiplexing)   
               시간을 나누어 모든 대역폭을 사용한다. 모든 대역폭을 사용하지만 일시적으로만 사용이 가능하다.   
         - DSL (digital subscriber line)   
            기존의 집전화를 생각하면 편할 것이다. ...   
               
         - home network   
            *구성*   
            WiFi AP > Router > Modem >>   
            그러나 현대의 AP는 라우팅 기능(목표 IP를 통해 적절한 홉으로 이동하도록 하는 기능)과 모뎀 기능(아날로그와 디지털을 변환시키는 기능)을 포함하는 경우도 있어서 AP만 두는 경우도 많다.   
               
            - Wireless access network   
               보통은 공유기를 지칭하며 Wireless는 broadcast(multiple)이며, half-duplex(반이중 : 한번에 통신을 보내고 받는 건 불가능, 두 기능 중 한번에 한가지만)이다. 그리고 외부 소음이나 장애물들(EX | 비)에 의해 영향을 받는다. 보통 Wireless local area(EX | WiFi)와 Wide-area cellular(EX | Cellular 4G/5G : 좁지만 파워가 강한 Cellular)가 있다. 차이점은 다음과 같다.   
                  
               범위 : Local < Wide   
               속도 : Local < Wide   
               다른 Wireless 연결은 Bluetooth(아주 짧은 범위, 제한된 속도), terrestrial microwave(P2P? IOT는 M2M?...), satelite(geostationary:정지 궤도의 경우 지연이 길기 때문에 모빌리티 통신에는 적합하지 않다.) 
         - enterprise network   
            주로 대학교와 기업에서 사용하는 네트워크로 WiFI와 Ethernet을 모두 사용하는 경우가 많다. BS를 통한 연결을 사용하지 않는 이유는 BS의 경우 각 개인의 Edge에 통신을 제공하기 때문에 적합하지 않다.   
         - datacenter network   
            데이터센터에서 통신은 크게 Extra(외부와의 통신), Intra(내부와의 통신) 두 가지로 나뉜다.
         
      - *Network core* : 각 edge 유저에게 제공하는 서비스가 아닌 통신에만 연결된 경우이다. 즉, 네트워크들의 네트워크이다. (EX local ISP, global ISP와 같은 것이다.) 해당 네트워크의 주 기능은 Forwarding, Routing 두 가지이다.   
         
         - Forwarding : switching으로 부르기도하며, 로컬 영역에서 라우터로 들어온 입력 링크를 적절한 출력 링크로 변경해주는 과정이다.

         - Routing : 출발지에서 목적지까지의 경로를 결정하는 과정으로 적절히 전달하기 위해 라우팅 알고리즘을 통해 라우팅 테이블이 작성된다.

         - packet-switching (shared=공유된)   
            패킷은 전달되기 전에 반드시 라우터에 도착하여야한다. 리소스를 평등하게 사용한다는 장점이 있다.   
               
            Queueing은 링크가 감당하기 어려운 속도로 도착하게 되면 진행되는 대기 방식이다. 만약 라우터의 버퍼보다 더 많은 값이 대기하게 되면 패킷의 손실이 일어난다.   
               
         - circuit-switching (dedicated=지정된)   
            보장된 회선이 있기 때문에 개인 서비스는 더 빠르게 사용이 가능하다. 과거의 전화 통신이 이렇게 이루어졌다.   
               
            보통 네트워크를 사용하는 유저가 모든 시간동안 네트워크를 사용하지 않기 때문에 회선 교환을 사용할 경우 리소스의 낭비가 심하다. 그러나 패킷 교환의 경우 공유된 리소스는 나눠쓰기 때문에 더 많은 유저들이 링크를 통해 네트워크를 사용할 수 있다.   

   *추가 상식 : CPU 코어의 3.41GHz와 같이 표시된 사양은 초당 3.41 x 10의6승 개의 instruction을 처리할 수 있다는 뜻이다.*   
               *패킷 통신 과정에서 upstream은 upload, downstream은 download를 뜻한다.*   
               *Modem의 약자는 Modulation, deModulation이다.





