# OSI 7 Layer
---
## What is OSI 7 Layer?
>OSI 7 Layer은, Open System Interconnection Reference Model의 줄임말로,  
우리가 사용하는 네트워크의 구성을 7개의 계층으로 모듈화(표준화) 시켜 놓은 것을 말한다.

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
TCP 나 UDP가 이 계층에 속한다.  

### Session Layer
>쉽게 생각하면, 채팅방을 생각하면 된다. 같은 세션끼리 연결하여 통신하는 것.
### Presentation Layer
>데이터의 인코딩이나, 암호화를 담당하는 계층이다.
### Application Layer
