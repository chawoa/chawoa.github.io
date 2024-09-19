---
title: 컴퓨터 네트워크 2 (Computer Networking)
date: 2024-09-19 23:00:40 +09:00
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
      총 delay : $$ d_{processing} $$ + $$ d_{queue} $$ + $$ d_{transmission} $$ + $$ d_{propagation} $$   
      - $$ d_{processing} $$ : bit error 검사 시간, 어떤 경로로 보낼 것인지에 대한 시간 $$   
      - $$ d_{queue} $$ : 출력 link에서의 전송을 기다리는 시간, 라우터에 혼잡도에 대해 영향을 받음   
      - $$ d_{transmission} $$ : 패킷의 길이 / link의 전송률 bps (link의 대역폭)   
         *패킷의 길이의 경우 사용하는 Application 따라 달라짐*   
      - $$ d_{propagation} $$ : link의 물리적 길이 / 전파 속도 (케이블 fiber 사용 시 최대인 $$ 2x10^8 $$ m/sec)   
      만약 라우터에 데이터가 도착하는 속도를 L (패킷의 평균 전송 속도 * 패킷의 길이)이라 하고, 데이터를 전송하는 속도를 R이라고 할때   
         L/R이 0에 가까울 경우 : 지연이 적음   
         L/R이 1에 가까울 경우 : 지연이 많음   
         L/R이 1보다 클 경우 : 지연이 무한대의 가능성   
   - Caravan analogy   
   - Traceroute   
   - Throughput   
      송신자가 수신자에게 보낸 데이터의 양을 나타내는 지표이다.    
      측정 방법은 instantaneous(측정 당시의 비율), average(장시간 측정한 값의 평균) 두 가지 이다.   
      라우터 하나를 사이에 두고, 데이터를 받고있는 link의 처리율보다 데이터를 보내는 link의 처리율이 느릴 경우 데이터 손실이 나타날 수 있다.   
      이러한 경우를 bottleneck link(다른 link들에 비해 상대적으로 작은 범위의 대역폭을 가지고 있어서 전송 속도에 영향을 주는 link)라고 한다. 실제에서는 각 서버나 기기의 경우 core network에 비해 bottleneck인 경우가 많다.   
         
      Core network 같은 경우 link가 공유되는 상황이 많다. 이런 경우 공유되는 link의 처리율을 사용하는 통신의 수로 나누면 된다. (EX. 처리율 / 10)  
- **Network Security**  
   - packet sniffing  
      packet sniffing은 공유된 Ethernet, wireless(wireless보다는 ethernet이 더 취약하다. wireless의 경우 해당 범위의 있는 모든 패킷을 다 확인해야하기 때문)에서 통신 시 제 3자가 모든 패킷을 읽고 저장하는 방법이다.  
   - IP spoofing  
      제 3자가 자신의 서버의 IP를 조작하여, 송신자의 데이터를 가져가거나, 다른 서버에 신뢰된 IP로 접속 및 데이터 전송을 할 수 있는 방법이다.  
   - DoS (Denial of Service)  
      공격자가 서버나 link의 대역폭과 같은 리소스들을 막대한 양의 트래픽 전송으로 사용이 불가능하게 만드는 방법이다.  
   - Solutions  
      - authentication : 사용자별 혹은 기기별 인증 절차를 통해 보안을 강화한다.  
      - confidentiality : 송/수신자만의 알고리즘을 통해 데이터의 내용을 알 수 있도록 보안을 강화한다.  
      - integrity checks : 각 사용자만 가지고 있는 고유의 코드를 통해 보안을 강화한다.(EX. 은행 OTP 카드)  
      - access restrictions : 허가되지 않은 IP로는 접근을 제한한다.  
      - firewall : 방화벽 설정을 통해 제한된 곳으로 부터 오는 요청을 거부하고, 한 번에 많은 양의 트래픽이나 주기적인 접근 요청에 대해 거부한다.  
- **Network Layering**  
   네트워크에서 계층화를 하는 이유 중 하나는 국제적인 표준을 만들기 위함이다.  
   - 단순한 네트워크 계층 구조  
      ![Layer](/assets/img/layer1.png){: width="500" height="500"}  
      - application : 네트워크를 제공해주는 서비스 (EX. HTTP, DNS, SMTP)  
      - transport : 프로세스간의 데이터 전송 주로 보안같은 신뢰성 관련 내용 (EX. TCP, UDP)  
      - network : 라우팅을 올바르게 할 수 있도록 적어주는 주소 관련 내용 (EX. IP)  
      - link : 근처의 네트워크에 전송하기 위한 정보 (EX. Ethernet, WiFi)  
      - physical : bit를 전송하는 물리적 연결  

      - 네트워크의 캡슐화와 역캡슐화  
         ![Layer](/assets/img/layer2.png){: width="500" height="500"}  
         스위치는 포워딩 기능만 존재하기 때문에 라우터처럼 적절한 경로를 탐색할 수 없다.  
         따라서 스위치에서는 캡슐안의 정보가 변화하지 않는다. 그러나 라우터의 경우 패킷안에 새로운 헤더 데이터가 캡슐화된다. 이는 다음 홉에 대한 주소를 넣어주기 위함이다.  