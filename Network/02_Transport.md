# Transport Layer 

## 통신계층에 대해서 설명해보세요.

- 통신계층은 호스트 간의 논리적 통신을 제공하는 네 번째 계층입니다.

## TCP

### TCP 연결의 특징에 대해서 설명해보세요.

- TCP 는 연결지향형 프로토콜로 신뢰성 있는 통신을 보장합니다. 따라서 매 통신마다 데이터를 송수신하기 전에 클라이언트와 서버가 연결을 설정해주어야 합니다. 또한 혼잡제어와 흐름제어를 제공한다는 특징도 있습니다.

### 3-Way Handshaking 을 설명해보세요.

- 3 way handshaking 은 TCP 프로토콜로 연결을 설정하는 과정을 의미합니다. 총 세 단계에 걸쳐 연결을 설정하기 때문에 3 way handshaking 이라고 합니다.
- 먼저 연결설정을 위해 클라이언트가 서버에 `TCP SYN` 요청을 보냅니다.
- 요청을 받은 서버는 `TCP SYN ACK` 로 응답하니다.
- 응답을 받은 클라이언트는 `TCP ACK` 을 다시 요청하고 TCP 연결이 설정됩니다.

### 이때 클라이언트와 서버의 상태는 어떤가요?

- 초기에 클라이언트와 서버는 모두 `CLOSED` 상태에 있습니다.
- 서버는 요청을 받을 준비가 되면 `LISTEN` 상태가 되어 클라이언트의 요청을 기다립니다. 
- 클라이언트는 서버에 요청을 보낸 뒤 TCP SYN ACK 을 기다리며 `SYN-SENT` 상태가 됩니다.
- 서버가 요청을 받은 뒤 TCP SYN ACK 을 보내면 `SYN-RECEIVED` 상태가 되어 클라이언트의 SYN ACK 을 기다립니다.
- TCP SYN ACK 을 받은 클라이언트는 서버와의 연결이 완성되었기 때문에 `ESTABLISHED` 상태로 전환되고 서버로 TCP ACK 을 전송합니다.
- TCP ACK 을 서버가 받게되면 두 클라이언트와 서버의 연결이 완성되었으므로 서버의 상태도 `ESTABLISHED` 상태가 됩니다.

### 4-Way Handshaking 을 설명해보세요.

- 4 way handshaking 은 TCP 프로토콜로 설정된 연결을 종료하기 위해 사용됩니다.
- 클라이언트가 서버와의 연결을 끊고자 할 때, 클라이언트는 서버에 `FIN` 패킷을 전송합니다.
- 서버는 `FIN` 요청을 받으면 `ACK` 으로 응답합니다.
- ACK 을 받은 클라이언트는 남은 패킷이 완전히 전달되기까지 일정 시간동안 기다립니다.
- 서버는 마지막 패킷까지 모두 전송한 뒤에 `FIN` 메세지를 전송하여 연결을 종료할 수 있음을 알립니다. 
- 클라이언트는 `ACK` 메세지를 다시 전송하여 서버의 연결 종료를 요청합니다.
- 요청을 받은 서버는 연결을 종료합니다.
- 클라이언트는 `FIN` 메세지보다 나중에 도착하는 패킷을 받기 위해 `MSL(Double Maimum Segment Life)` 시간동안 대기합니다.
- 대기 시간이 끝나고 클라이언트는 연결을 완전히 종료합니다.

### 이때 클라이언트와 서버의 상태는 어떤가요?

- 초기에는 서버와 클라이언트가 연결된 상태에 있으므로 양쪽 모두 `EATABLISEHD` 상태를 가집니다. 
- 클라이언트는 종료를 요청하는 FIN 메세지를 전송하고, 서버의 ACK 메세지를 기다리는 `FIN-WAIT-1` 상태가 됩니다.
- 이때 서버는 FIN 메세지를 받고 ACK 메세지를 전송한 뒤, `CLOSE-WAIT` 상태가 됩니다.
- 서버의 ACK 메세지를 받은 클라이언트는, 서버의 FIN 메세지를 기다리며 `FIN-WAIT-2` 상태가 됩니다.
- 서버는 자신이 가진 패킷을 모두 전송하고 FIN 메세지를 전송한 뒤 `LAST-ACK` 상태가 됩니다. 
- 클라이언트는 FIN 메세지를 받은 뒤, 서버로 ACK 메세지를 보내고 나머지 패킷을 기다리며 `TIME-WAIT` 상태가 됩니다.
- 서버는 클라이언트의 ACK을 받게되면 연결을 종료하기 때문에 `CLOSED` 상태가 됩니다.
- 클라이언트는 일정시간 기다리고 연결을 종료한 뒤 `CLOSED` 상태가 됩니다.

### TCP 헤더에 Squence Number 필드가 필요한 이유를 설명해보세요.

- TCP는 항상 패킷의 순서를 보장해야합니다. 따라서 쪼개져있는 세그먼트에 번호를 붙여서 각 패킷이 따로 도착한다고 하더라도 순서대로 다시 재조합할 수 있도록 합니다.

### 그럼 Sequence Number 필드랑 Acknowledgement Number 필드의 차이는 뭐예요?

- Acknowledgement Number 는 서버로부터 받아야할 다음 데이터의 Sequence Number를 나타냅니다.

### 혼잡제어와 흐름제어의 차이를 말해보세요.

- 혼잡제어(Congestion Control)는 네트워크에 패킷이 과도하게 들어오는 것을 막습니다. 송신자가 데이터를 보내는 속도와 네트워크가 데이터를 처리하는 속도의 차이가 있어 문제가 발생합니다. 
- 흐름제어(Flow Control)는 송신 호스트의 속도가 수신 호스트의 처리 속도보다 빨라 수신 호스트의 라우터 큐를 초과하게 되는 상황을 제어하는 것을 말합니다.

### TCP가 흐름제어를 어떻게 하는지 설명해보세요.

- TCP 는 Stop-and-Wait 방식이나 Sliding Window 방식을 사용하여 흐름제어를 수행합니다.
- `Stop-and-Wait`는 송신자가 자신이 전송한 패킷에 대한 ACK 을 받아야 다음 패킷을 전송할 수 있도록 하는 방식입니다.
- `Sliding Window` 방식은 수신측과 송신측에 윈도우라는 버퍼를 두고 알고리즘에 따라 전송할 세그먼트의 번호와 수신할 세그먼트의 수신번호의 영역을 설정하여 한번에 전송할 수 있는 세그먼트의 양을 제한하여 흐름을 제어하는 방십니다. 

### 그럼 TCP가 혼잡제어는 어떻게 하는지 설명해보세요.

- 혼잡제어는 크게 `AIMD(Additive Increase Multicative Decrease)` 와 `Slow Start` 를 사용하여 수행합니다. 
- AIMD는 네트워크가 혼잡하지 않아 전송속도를 늘릴 수 있을 때는 1 씩 증가시키고, 혼잡제어를 위해 전송속도를 줄일 때는 반으로 윈도우의 크기를 줄여 전송할 패킷의 개수를 줄여주는 방법입니다.

## UDP

### UDP 의 특징에 대해서 설명해보세요.

- UDP는 비 연결형 서비스로 데이터그램 방식으로 데이터를 송수신하는 프로토콜입니다. 신뢰적 통신을 보장하지는 않지만 빠른속도로 데이터를 송수신할 수 있어 스트리밍 같은 빠른 반응이 필요한 서비스에 사용됩니다.

## SSL/TLS

### SSL 에 대해서 설명해보세요.

- SSL은 Application Layer 와 Transport Layer 사이에서 데이터를 암호화/복호화하여 양 계층에 전달하는 암호화 통신 프로토콜입니다.

### SSL의 통신과정을 설명해보세요.

- SSL 은 기존 TCP 3-way handshaking 과정에 SSL Handshaking 을 추가하여 사용합니다. 
- 클라이언트는 서버에 client hello 메세지를 보냅니다. 이때 랜덤한 데이터를 생성하여 함께 보냅니다.
- 서버는 요청을 받은 뒤 server hello 로 응답하면서 인증서와 암호화 방식, 서버에서 랜덤하게 생성한 데이터를 응답으로 전달합니다.
- 클라이언트는 서버가 보낸 인증서가 CA에 의해 발급된 인증서인지 확인합니다. 유효한 인증서라면 클라이언트는 대칭키를 생성한 뒤 인증서에 포함된 공개키로 대칭키를 암호화하여 서버에 전송합니다. 
- 서버는 자신이 가진 개인키로 암호화된 대칭키를 복호화합니다.
- 이제 양쪽 호스트는 모두 대칭키를 가지게 되었고 이 키를 사용하여 통신시 전달되는 데이터를 암호화하고 복호화합니다.