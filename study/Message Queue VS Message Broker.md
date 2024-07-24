# Message Queue vs Message Broker

- https://dreamix.eu/insights/message-queue-vs-message-broker-whats-the-difference/



## Message Queue

### Queue

- FIFO(First In First Out) Data Structure



### Message Queue

- 데이터를 전송할 때 사용하는 Data Structure (메시지를 전달)
- Producers : 메시지를 큐에 저장
- Consumers : 메시지를 수신
- 일종의 통신 메커니즘으로, 송신자와 수신자 간의 비동기 통신을 가능하게 함



## Message Broker

- 서로 다른 애플리케이션 간의 안정적이고 신뢰할 수 있는 통신을 제공하는 소프트웨어
- 서로 다른 언어를 사용하고 같은 기술 스택을 사용하지 않더라도 괜찮음. 메시지 프로토콜 간의 정보를 번역하는 것이 메시지 브로커의 역할임
- 정보를 저장하고, 라우팅하며, 원하는 목적지로 전달하는 역할을 수행
- 일반적으로 메시지 브로커의 목적은 애플리케이션 내부적으로 통신할 수 있게 통신 계층의 역할을 수행
- 송신자는 수신자가 누구인지, 몇 명인지, 심지어 수신자들이 활성화되어 있는지 조차 알지 못한채 메시지 전송이 가능



## Different Messaging Style

### Point-to-point messaging

- 메시지 큐를 사용하여 메시지의 송신자와 수신자가 1:1 관계를 갖는 방식
- 이 유형의 메시징 스타일은 각 메시지가 단 한번만 전송되고 소비될 것을 보장할 때 사용



### Publish-subscribe messaging

- 메시지 생성자가 메시지를 특정 주제(Topic)으로 보내도록 함
- 소비자들은 이러한 토픽을 구독하고, 생성자가 보낸 정보를 수신함
  - 송신자와 수신자간의 관계가 1:N 관계
- 메시지가 특정 토픽에 게시되면, 그 토픽을 구독한 모든 사람에게 메시지가 전달 됨



## Message Queue vs Message Broker, The difference

- Message Queue
  - Queue 데이터 구조를 사용하여 메시지를 보내고, 받고, 저장함으로써 애플리케이션 간의 통신을 용이하게 함
  - 메시지 큐는 데이터 전송에 사용되지만 자신이 운반하는 정보를 읽을 수는 없음
- Message Broker
  - 메시지 큐의 사용을 확장하는 메커니즘
  - 메시지 큐와 달리, 메시지 브로커는 자신을 통해 전달되는 정보의 내용을 읽을 수 있음
  - 또한, 메시지 브로커는 파일이나 HTTP 요청에서 읽은 정보와 같은 다양한 출처의 정보를 처리할 수 있음
  - 요약하면, 메시지 브로커는 아래와 같은 역할을 함
    - 데이터 전송 프로토콜 간의 변환
    - 서비스 간 메시지 형식의 변환
    - 서비스 간 통신의 라우팅
    - 다양한 출처에서 발생하는 이벤트의 분배
  - 메시지 브로커는 메시지 큐를 사용하여 모든 관련된 당사자 간에 정보를 전송
- Message Queue : 생성된 데이터를 소비될 때까지 저장하는 구조
- Message Broker : Message Queue를 관리하는 소프트웨어 컴포넌트