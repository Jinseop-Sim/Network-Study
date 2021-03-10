# Layered Architecture
---
## Layered Architecture  
>- 네트워크는 서로 영향을 끼치지 않는 각각의 독립적인 계층 구조로 존재한다.  
>- 각 층은 반드시 한 단계 아래층만의 정보를 받아서 행동한다.  
>- 각 층은 반드시 한 단계 위층으로만 정보를 제공한다.  

![LAP](https://user-images.githubusercontent.com/71700079/110340397-8fa96a00-806c-11eb-8284-9373175e5774.png)  

## Layered Protocol Architecture
>- 위에서 본 각 Layer들이 일을 하기 위해서는 통신할 대상이 있어야 하는데, 그 대상을 __Peer Layer__ 이라고 칭한다.
>- 이 때 여러개의 __Peer Layer__ 들 끼리 여러개의 __Protocol__ 을 가지고 동작을 하는 구조를 우리는 _Layered Protocol Architecture_ 이라고 한다.  

## Elements of Protocol
- Syntax : 문법적인 요소, 메세지의 형식을 의미한다.(txt, bin, ...)
- Semantic : 의미적인 요소, 일의 처리 방식과 에러의 처리 방식을 의미한다.
- Timing : 시간적인 요소, 일을 처리할 순서 및 __Synchronization(동기화)__ 에 대한 요소이다.  

## Protocol Data Unit(PDU)
- Protocol Data Unit(PDU) : PCI와 SDU가 합쳐진 데이터
- Protocol Control Information : 헤더의 역할, 제어 정보를 담고있는 머리 부분이다.
- Service Data Unit : 프로토콜이 서비스를 제공할 대상, 수신자.  
![제목 없음](https://user-images.githubusercontent.com/71700079/110626438-103ea680-81e4-11eb-80aa-31ca5988a763.png)  

>이렇게 높은 계층에서부터 헤더가 앞에 하나씩 붙게 된다.  
즉, 제일 낮은 계층이 제일 앞에 붙어있게 된다.  

## Standard Protocol
- Why Standard Protocol is needed? : 장비들과의 소통이 무조건 요구되며, 통일된 규약이 필요하다. 따라서 판매자들이 더욱 marketable한 상품을 만들 수 있게 된다.
- De Facto Standard : 보통 통상적으로 사용하는 __Standard Protocol__ 으로, __TCP/IP의 Protocol Suite__ 가 이에 해당한다. (미국에서 많이 사용)
- De Jure Standard : 명목적인, 법률로 제정하여 기준을 잡아놓은 것으로, __OSI Reference Model__ 이 이에 해당하며, ISO에서 제정한다. (유럽, 중국 등이 사용)  

## What is OSI 7 Layer?
>OSI 7 Layer은, Open System Interconnection Reference Model의 줄임말로,  
우리가 사용하는 네트워크의 구성을 ISO에서 7개의 계층으로 모듈화(표준화) 시켜 놓은 것을 말한다.  
이는 위에서 언급했듯이, __De Jure Standard__ 에 속한다. 

## Why we use OSI 7 Layer?
>쉽게 예를 들어, 우리가 자동차를 고친다고 가정을 해보자.  
우리는 자동차가 고장이 나면, 어떤 기능 / 부품에 문제가 있는지 부터 파악을 하고 그 부분만 고치게 된다.  
그러한 과정이 용이하기 위해서 정비사에서는 이미 각 기능과 부품 별로 정리를 해놓은 모듈이 있을 것이다.  
이렇게, 문제가 발생했을 시 접근과 복구를 용이하게 하기 위해 네트워크 구성을 모듈화 한 것이 OSI 7 Layer이다.

## OSI 7 Layer
1. 물리 계층(Physical Layer - Hardware)
2. 데이터링크 계층(Datalink Layer - Hardware + Software)
3. 네트워크 계층(Network Layer - Software)
4. 전송 계층(Transport Layer - Software)
5. 세션 계층(Session Layer - Software)
6. 표현 계층(Presentation Layer - Software)
7. 응용 계층(Application Layer - Software)

### Physical Layer
>물리 계층은 전기적, 기계적인 데이터 전달만 담당한다.  
On과 Off 즉, 0과 1로만 이루어져있으며, 데이터가 어떤 데이터든 간에 전달만 하는 장치이다.  
대표 장비 : __리피터(전기 신호 증폭 장치)__ 와 __허브(연결된 장비에 전기 신호 전달 및 증폭)__  

### Datalink Layer
>데이터의 단위는 __프레임__ , Physical Layer을 참조하여 이것을 만들어 주고받도록 한다.  
대표 장비 : __스위치, 브리지, 랜카드__ , 목적지(특정 Port)로 Frame을 전달하는 역할을 맡는다.  

### Network Layer
>데이터의 단위는 __패킷__, 라우터나 릴레이를 이용하여 다수의 링크를 연결해준다.  
__Internet Protocol__ , 즉 __IP__ 가 이 계층에 속한다.  
대표 장비 : __라우터, L3 스위치__ , 다른 네트워크와 통신을 하려면 반드시 이 장치들을 거쳐야 한다.  
목적지의 IP 주소를 보고, 목적지와 연결된 인터페이스를 통해 전송을 결정하는데, 이를 __라우팅(Routing)__ 이라고 한다.  

### Transport Layer
>종단(End System) 간의 데이터 교환을 담당한다. 접속 관리 및 오류 제어 담당.  
__TCP/UDP__ 가 이 계층에 속한다.  

### Session Layer
>쉽게 생각하면, 채팅방을 생각하면 된다. 같은 세션끼리 연결하여 통신하는 것.  

### Presentation Layer
>데이터의 인코딩이나, 암호화를 담당하는 계층이다.  

### Application Layer
>파일 전송, 원격 접속, 전자 거래, 메시지 처리 및 교환 등의 실제 사용하는 기능들을 담당하는 계층이다.  
![Heleeo](https://user-images.githubusercontent.com/71700079/110627684-9d362f80-81e5-11eb-9a40-0a5c31f2f516.png)  

## Difference between OSI Layers and TCP/IP  
![TCP](https://user-images.githubusercontent.com/71700079/110628521-72001000-81e6-11eb-9388-c0519178cb3a.PNG)
