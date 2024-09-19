---
title: 컴퓨터 네트워크 2 (Computer Networking)
date: 2024-09-19 15:00:40 +09:00
categories: [이론, 컴퓨터 네트워크]
tags: [컴퓨터 네트워크, Computer Networking]
mermaid: true
math: true
---

# 컴퓨터 네트워크 2 (Computer Networking)   

- **CORE Network(Back-Bone)**   
모든 access net끼리 연결할 경우 O(N*N)의 연결이 생성되기 때문에 합리적이지않다. 따라서 Global ISP와 같이 Core-network를 두어 합리적으로 통신하기 위해 나타났다.   
각 나라에도 여러 Core-network가 존재한다. 이들이 통신간에 모두 같은 프로토콜을 사용한다면, peering-link로도 연결이 가능하다. 그러나 대부분의 Core-network들은 각자 다른 프로토콜을 가지기 때문에 IXP(Internet exchange point EX. GW)를 통해 서로 통신해야한다.   
   - 일반적인 인터넷 구조   
      ![Desktop View](/assets/img/internet-st.png){: width="500" height="500"}
      Tier-1 ISP : 국내외 범위의 ISP (EX. SKT... 국제적으로는 Tier-2이다.)   
   - Content provider network : 분산된 네트워크를 통해 서로 통신하며 사용자에게 서비스를 제공하는 네트워크. 보통 tier-1 혹은 지역 ISP를 통해 제공한다. (EX. 네이버)   

*추가*   
   - 하나의 ISP에서 access net(서비스를 제공하는 네트워크)으로 제공되는 연결의 경우는 intraconnected이며, 두 개 이상의 ISP가 연결되어있는 것을 interconnected라고 한다.   

- **Delay&Loss&Throughput**   
   - 라우터의 주요 2가지 기능 : 다음 적절한 홉으로의 경로 제공, 패킷을 받을 때 Queue로 버퍼를 만들어서 처리   
      이 전송 과정에서 적절한 목적지를 찾으면서 delay가 생기고 해당 delay를 Process delay라고 칭하기도 한다. 또한 link의 처리량이 패킷이 오는 속도 보다 느리게 되면 통신해야할 패킷은 Queue에 대기해야한다. 이 부분에서도 추가 지연이 발생 할 수 있다. 만약 전달 받고 있는 패킷이 Queue에 넘치게 되면 데이터 손실이 나타난다.   
   - delay의 4종류   
      총 delay : d_{processing} + d_{queue} + d_{transmission} + d_{propagation}   
      - d_{processing} : bit error 검사 시간, 어떤 경로로 보낼 것인지에 대한 시간   
      - d_{queue} : 출력 link에서의 전송을 기다리는 시간, 라우터에 혼잡도에 대해 영향을 받음   
      - d_{transmission} : 패킷의 길이 / link의 전송률 bps (link의 대역폭)   
         *패킷의 길이의 경우 사용하는 Application 따라 달라짐*   
      - \$$ d_{propagation} : link의 물리적 길이 / 전파 속도 (케이블 fiber 사용 시 최대인 2x10^8m/sec) $$
      만약 라우터에 데이터가 도착하는 속도를 L (패킷의 평균 전송 속도 * 패킷의 길이)이라 하고, 데이터를 전송하는 속도를 R이라고 할때   
         L/R이 0에 가까울 경우 : 지연이 적음   
         L/R이 1에 가까울 경우 : 지연이 많음   
         L/R이 1보다 클 경우 : 지연이 무한대의 가능성   
   - Caravan analogy   
   - Traceroute   
   - Throughput   

      

