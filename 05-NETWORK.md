<!--
<details>
  <summary><b></b></summary>

  ---
  
  <details>
    <summary></summary>
  </details>

  ---
</details>
-->

## 네트워크 기초

<details>
  <summary><b>좋은 네트워크란 어떤 네트워크인가요?</b></summary>

  - 많은 처리량, 짧은 지연시간, 낮은 장애 빈도, 좋은 보안 등을 갖춘 네트워크가 좋은 네트워크라 생각합니다. 

  ---

  <details>
    <summary>트래픽이란?</summary>

    - 특정 시점에 흐르는 데이터 양을 뜻합니다.
    - 예를 들어, 서버에 저장된 파일을 클라이언트가 다운로드하는 요청이 발생했을 때, 발생되는 데이터 누적량을 뜻합니다.
    - 단위) BPS(Bits Per Second) : 초당 전송/수신되는 비트 수를 의미 
    - Ex) 10MB 동영상 10명이 다운 시 누적 트래픽 량 = 10 * 10 = 100MB 
  </details>
  <details>
    <summary>처리량이란?</summary>

    - 성공적으로 전달되는 데이터의 양을 말하는 것으로 보통 트래픽 처리량을 뜻합니다.
    - 즉, 대용량 트래픽을 처리한다는 것은 높은 처리량을 가진 것입니다.
    - 단위) BPS(Bits Per Second) : 초당 전송/수신되는 비트 수를 의미
  </details>
  <details>
    <summary>트래픽과 처리량의 차이는?</summary>

    - 트래픽이 많아졌다는 것 = 흐르는 데이터가 많아졌다는 것
    - 처리량이 많아졌다는 것 = 처리되는 트래픽이 많아졌다는 것
  </details>
  <details>
    <summary>대역폭이란?</summary>

    - 주어진 시간동안 네트워크 연결을 통해 흐를 수 있는 최대 비트 수를 말합니다.
    - 즉, 최대 처리할 수 있는 트래픽을 뜻하는 것으로 최대 동시 접속자 수를 유추하는 데 척도가 됩니다.
    - 때문에, 대역폭이 클수록 사용자에게 빠른 서비스를 제공할 수 있습니다.
    - 단위) BPS(Bits Per Second) : 초당 전송/수신되는 비트 수를 의미
  </details>
  <details>
    <summary>RTT(Round Trip Time; 왕복 지연 시간)란?</summary>
    
    - 신호를 전송하고 해당 신호의 수신 확인에 걸린 시간을 더한 값입니다.
    - 예를 들어, 어떤 메시지가 두 장치 사이를 왕복하는 데 걸린 시간이 RTT라 할 수 있습니다.
    - 지연시간: 매체타입(무선, 유선), 패킷 크기, 라우터의 패킷 처리 시간에 영향을 받습니다.
  </details>

  ---
</details>
<details>
  <summary><b>병목 현상이란 무엇인가요?</b></summary>

  - 일반적으로 전체 시스템의 성능이나 용량이 하나의 구성요소로 인해 제한을 받는 현상을 말합니다. 즉, 네트워크에서는 트래픽에 의해 데이터 흐름이 제한되는 상황을 말합니다.
  - 예를 들어, 병의 몸통보다 병의 목 부분의 내부 지름이 좁아 물이 상대적으로 천천히 쏟아지는 것에 비유할 수 있습니다. 
  - 만약, 서비스에서 이벤트를 열었을 때 트래픽이 많이 생기고 그 트래픽을 잘 관리하지 못하면 병목 현상이 생겨 사용자는 웹 사이트로 들어가지 못하게 됩니다.

  ---

  <details>
    <summary>병목 현상의 원인은 무엇일까요? (답변 미작성)</summary>
  </details>
  <details>
    <summary>병목현상을 어떻게 해결할 수 있을까요? (답변 미작성)</summary>
  </details>
  <details>
    <summary>성능 테스트 시, 중요 시 보는 게 있나요? (답변 미작성)</summary>
  </details>
  <details>
    <summary>네트워크 성능 분석 명령어에 대해 아시는 게 있나요?</summary>

    - ping
      - 네트워크 상태를 확인하려는 대상 노드를 향해 일정 크기의 패킷을 전송하는 명령어
      - 이를 통해 해당 노드의 패킷 수신 상태와 도달하기까지 시간, 네트워크 연결 상태 등을 확인할 수 있다.
      - TCP/IP 프로토콜 중 ICMP 프로토콜을 통해 동작한다.
    - netstat
      - 접속되어 있는 서비스들의 네트워크 상태를 표시하는 데 사용된다.
      - 이는 네트워크 접속, 라우팅 테이블, 네트워크 프로토콜 등의 리스트를 보여준다.
      - 주로 서비스의 포트가 열려 있는 지 확인하기 위해 사용된다.
    - nslookup
      - DNS에 관련된 내용을 확인하기 위해 쓰는 명령어로 특정 도메인에 매핑된 IP를 확인하기 위해 사용된다.
    - tracert(윈도우) 혹은 traceroute(리눅스)
      - 목적지 노드까지 네트워크 경로를 확인할 때 사용하는 명령어
      - 목적지 노드까지의 구간들 중 어느 구간에서 응답 시간이 느려지는 지 등을 확인할 수 있습니다.  
  </details>

  ---
</details>
<details>
  <summary><b>유니캐스트, 멀티캐스트, 브로드캐스트에 대해 설명해주세요.</b></summary>

  - 유니캐스트
    - 1 : 1 통신이다. 대표적으로 HTTP 통신이 있다.
  - 멀티캐스트
    - 1 : N 통신이다. 이때 N은 연결된 모든 노드들이 아닌 특정 그룹의 노드들에게만 데이터를 전달한다.
  - 브로드캐스트
    - 1 : N 통신이다. 이때 N은 그룹이 아닌 연결된 모든 노드들을 말한다. 대표적으로 ARP가 있다.

  ---
</details>
<details>
  <summary><b>LAN, MAN, WAN에 대해 설명해주세요.</b></summary>

  - LAN
    - MAN, WAN보다 높은 안정성, 전송 속도를 가진다.
    - 일반적으로 허브, 스위치로 연결된 소규모 네트워크를 말한다. (집, 사무실 등) 
    - 하나의 IP 주소(논리적)를 기반으로 여러 개의 MAC 주소(물리적)로 구별하는 네트워크라 볼 수 있다.
    - 내부적으로는 하나의 IP 주소를 받았지만 NAT(라우터) 기술을 통해 여러 IP인 것처럼 가상의 IP를 부여하고 각 컴퓨터 고유 번호인 MAC 주소를 기반으로 구별한다.
    - 외부적으로는 논리적 주소인 IP 주소를 기반으로 통신한다.
  - MAN
    - 도시와 도시의 통신망을 뜻하는 것으로 2개 이상의 LAN이 연결되어 구성된다.
    - 연결은 라우터, 브리지 등으로 연결된다. (브릿지 = LAN과 LAN을 잇는 네트워크 장치)
  - WAN
    - 국가와 국가와의 통신망으로 수많은 라우터를 거쳐 다른 국가와도 연결되는 범위를 말한다.

  ---
</details>

## 네트워크 계층

<details>
  <summary><b>OSI 7계층에 대해 설명해 주세요.</b></summary>

  - 네트워크 통신이 일어나는 과정을 7단계로 나눈 네트워크 표준 모델입니다.
  - 즉, 네트워크 프로토콜이 통신하는 구조를 7개의 계층으로 분리해 각 계층간 상호 작동하는 방식을 정해놓은 것입니다.
  - 이는 응용, 표현, 세션, 전송, 네트워크(패킷), 데이터 링크(프레임), 물리(비트) 계층으로 이루어져 있습니다. 

  ---

  <details>
    <summary>각 계층을 간단하게 설명해주세요.</summary>

    - 응용 계층 (L7)
      - 최종 목적지로 응용 프로세스와 직접 관계하여 일반적인 응용 서비스를 수행합니다.
      - 사용자 인터페이스(UI), 전자우편, DB 관리 등의 서비스를 제공합니다.
      - Ex: HTTP, FTP, DNS 등
    - 표현 (L6)
      - 데이터 표현에 대한 독립성을 제공하고 암호화하는 역할을 담당하는 계층입니다. 즉, 파일 인코딩, 명령어 포장, 압축, 암호화 등을 합니다.
      - Ex: JPEG, MPEG 등
    - 세션 계층 (L5)
      - 데이터가 통신하기 위한 논리적 연결을 담당하는 계층입니다. 즉, TCP/IP 세션을 관리하는 책임을 갖습니다.
      - Ex: API, Socket 등
    - 전송 계층 (L4)
      - TCP/UDP 프로토콜을 통해 통신을 활성화하는 계층입니다. 즉, 포트를 열어서 프로그램들이 데이터를 주고 받을 수 있도록 합니다.
      - TCP: 신뢰성, 연결형, 패킷 교환 방식, 느림, 순서 보장 O, 1:1 통신, 수신 여부 확인 O
      - UDP: 비신뢰성, 비연결형, 데이터그램 방식, 빠름, 순서 보장 X, N:N 통신, 수신 여부 확인 X, 실시간
    - 네트워크 계층 (L3)
      - 데이터를 목적지까지 가장 안전하고 빠르게 전달하는 기능을 담당하는 계층으로 라우팅, 흐름 제어, 세크멘테이션, 오류 제어 등을 수행합니다.
      - 이 계층은 라우터를 통해 이동할 경로를 선택하여 IP 주소를 지정하고 해당 경로에 패킷을 전달합니다.
      - 전송 단위: 패킷
      - Ex: 라우터, IP 
    - 데이터 링크 계층 (L2)
      - 물리 계층으로 송/수신되는 정보를 관리하여 안전하게 전달되도록 도와주는 계층입니다.
      - 이 계층은 MAC 주소를 기반으로 통신합니다. 즉, 프레임에 물리적 주소인 MAC 주소를 부여해 오류 제어, 흐름 제어를 수행합니다. 
      - 전송 단위: 프레임
      - Ex: 브리지, 스위치, 이더넷 등
    - 물리 계층 (L1)
      - 데이터를 전기적 신호로 변환해 주고 받는 기능을 수행하는 계층입니다. 즉, 데이터를 전송하는 역할만 수행합니다.
      - 전송 단위: 비트 (전기적 신호, 0/1)
      - Ex: 통신 케이블, 리피터, 허브 등
  </details>
  <details>
    <summary>스위치와 라우터의 차이에 대해 말씀해주세요. (답변 미작성)</summary>
  </details>
  <details>
    <summary>전송 계층과 네트워크 계층의 차이에 대해 말씀해주세요. (답변 미작성)</summary>
  </details>

  ---
</details>
<details>
  <summary><b>TCP/IP 4계층에 대해 설명해주세요.</b></summary>

  - OSI 7 계층 모델은 실무적으로 이용하기에 다소 복잡하여 TCP/IP 프로토콜 통신 과정에 초점을 맞추어 더 단순화한 계층이다.
  - 이는 응용, 전송, 인터넷, 네트워크 엑세스 계층으로 구성된다.  

  ---

  <details>
    <summary>각 계층을 간단하게 설명해주세요.</summary>

    - 응용 계층 (OSI 7 계층의 응용 계층 + 표현 계층 + 세션 계층) 
      - 사용자에게 서비스를 제공하는 계층이다.
      - Ex: HTTP, SMTP, SSH, FTP 등
    - 전송 계층
      - 응용 계층과 인터넷 계층 사이에서 데이터가 전달될 때 중계 역할을 하는 계층입니다.
      - 즉, 응용 계층에서 받은 메시지를 기반으로 세그먼트 혹은 데이터그램으로 데이터를 쪼개 전달합니다.
      - Ex: TCP(세그먼트), UDP(데이터그램)
    - 인터넷 계층 (OSI 7계층의 네트워크 계층)
      - 전송 계층에서 받은 세그먼트 혹은 데이터그램을 패킷화하여 IP 주소로 지정된 목적지로 전송하는 역할을 담당하는 계층이다.
      - 전송 계층과 다르게 수신 쪽에서 패킷을 잘 받았는 지에 대해 보장하지 않는 비연결형 특징을 가지고 있는 데이터그램 방식이다.
      - Ex: IP, ARP, ICMP
    - 네트워크 엑세스 계층 (OSI 7 계층의 데이터 링크 계층 + 물리 계층)
      - 실질적으로 데이터가 네트워크를 통해 물리적으로 전달되며 장치 간 신호를 주고 받는 계층이다.
      - Ex: 전선, 광섬유, 무선 등
  </details>

  ---
</details>
<details>
  <summary><b>계층 간 송/수신 흐름을 말해보세요.</b></summary>

  - 캡슐화
    1. 송신측의 응용 계층 데이터가 전송 계층으로 전달되며 TCP(L4) 헤더가 붙고 세그먼트 또는 데이터그램화 됩니다.
    2. 인터넷 계층으로 전달되며 IP(L3) 헤더가 붙고 패킷화 됩니다.
    3. 네트워크 엑세스 계층으로 전달되며 프레임 헤더와 프레임 트레일러가 붙고 프레임화 됩니다.
  - 비캡슐화
    4. 수신 측에서 캡슐화된 데이터를 받습니다.
    5. 네트워크 엑세스 계층에서 인터넷 계층으로 전달되면서 프레임화된 데이터가 다시 패킷화됩니다.
    6. 전송 계층으로 전달되면서 패킷화된 데이터가 세그먼트 혹은 데이터그램화 됩니다.
    7. 응용 계층으로 전달되면서 메시지화 됩니다.
    8. 최종적으로 사용자에게 애플리케이션의 PDU만 받습니다.

  ---

  <details>
    <summary>캡슐화와 비캡슐화에 대해 설명해주세요.</summary>

    - 캡슐화 과정
      - 상위 계층의 헤더와 데이터를 하위 계층의 데이터 부분에 포함시키고 해당 계층의 헤더를 삽입하는 과정을 말한다.
      - 즉, 송신자가 수신자에게 데이터를 보낼 때 데이터가 각 계층을 지나면서 각 계층의 특징들이 담긴 헤더들이 붙여지는 과정이다.
      - 예를 들어, 전송 계층은 TCP 헤더, 네트워크 계층은 IP 주소 헤더를 추가한다.
    - 비캡슐화 과정
      - 하위 계층에서 상위 계층으로 이동하며 각 계층의 헤더 부분을 제거하는 과정이다.
      - 즉, 캡슐화의 역과정으로 수신자 측에서 캡슐화된 데이터를 역순으로 제거하며 응용 계층까지 도달한다.
  </details>
  <details>
    <summary>PDU(Protocol Data Unit)란?</summary>

    - 네트워크의 어떠한 계층에서 계층으로 데이터가 전달될 때 한 덩어리의 단위를 말하는 것으로 각 계층마다 부르는 명칭이 다르다. 
    - 즉, TCP/IP 4계층을 기반으로 설명했을 때 각 계층의 데이터 단위를 의미하는 것으로 헤더, 데이터를 의미하는 페이로드로 구성되어 있다. 
    - PDU는 아래 계층인 비트로 송수신하는 것이 가장 빠르고 효율성이 좋지만 확장성 등의 이유로 응용 계층에서는 문자열 기반으로 송수신을 한다.  
  </details>
  <details>
    <summary>각 계층의 PDU(Protocol Data Unit)를 말해주세요.</summary>

    - 응용 계층: 메시지
    - 전송 계층
      - TCP: 세그먼트
      - UDP: 데이터그램
    - 인터넷 계층: 패킷 (세그먼트 혹은 데이터그램에 IP 헤더가 붙은 형태의 조각)
    - 네트워크 엑세스
      - 데이터 링크 계층: 프레임 (MAC 주소 헤더와 CRC/Checksum 트레일러가 붙은 조각)
      - 물리 계층: 비트
  </details>
  <details>
    <summary>CRC/Checksum Trailer란? (답변 미작성)</summary>
  </details>

  ---
</details>

## TCP/UDP

<details>
  <summary><b>TCP와 UDP의 차이에 대해 설명해 주세요.</b></summary>

  ---

- Checksum이 무엇인가요?
- TCP와 UDP 중 어느 프로토콜이 Checksum을 수행할까요?
- 그렇다면, Checksum을 통해 오류를 정정할 수 있나요?
- TCP가 신뢰성을 보장하는 방법에 대해 설명해 주세요.
- TCP의 혼잡 제어 처리 방법에 대해 설명해 주세요.
- 왜 HTTP는 TCP를 사용하나요?
- 그렇다면, 왜 HTTP/3 에서는 UDP를 사용하나요? 위에서 언급한 UDP의 문제가 해결되었나요?
- 그런데, 브라우저는 어떤 서버가 TCP를 쓰는지 UDP를 쓰는지 어떻게 알 수 있나요?
- 본인이 새로운 통신 프로토콜을 TCP나 UDP를 사용해서 구현한다고 하면, 어떤 기준으로 프로토콜을 선택하시겠어요?

  ---
</details>
<details>
  <summary><b>3-Way Handshake에 대해 설명해 주세요.</b></summary>

  ---

- ACK, SYN 같은 정보는 어떻게 전달하는 것 일까요?
- 2-Way Handshaking 를 하지않는 이유에 대해 설명해 주세요.
- 두 호스트가 동시에 연결을 시도하면, 연결이 가능한가요? 가능하다면 어떻게 통신 연결을 수행하나요?
- SYN Flooding 에 대해 설명해 주세요.
- 위 질문과 모순될 수 있지만, 3-Way Handshake의 속도 문제 때문에 이동 수를 줄이는 0-RTT 기법을 많이 적용하고 있습니다. 어떤 방식으로 가능한 걸까요?

  ---
</details>
<details>
  <summary><b>4-Way Handshake에 대해 설명해 주세요.</b></summary>

  ---

- 패킷이 4-way handshake 목적인지 어떻게 파악할 수 있을까요?
- 빨리 끊어야 할 경우엔, (즉, 4-way Handshake를 할 여유가 없다면) 어떻게 종료할 수 있을까요?
- 4-Way Handshake 과정에서 중간에 한쪽 네트워크가 강제로 종료된다면, 반대쪽은 이를 어떻게 인식할 수 있을까요?
- 왜 종료 후에 바로 끝나지 않고, TIME_WAIT 상태로 대기하는 것 일까요?

  ---
</details>

## IP
<details>
  <summary><b>IP 주소는 무엇이며, 어떤 기능을 하고 있나요?</b></summary>

  ---

  - IPv6는 IPv4의 주소 고갈 문제를 해결하기 위해 만들어졌지만, 아직도 수많은 기기가 IPv4를 사용하고 있습니다. 고갈 문제를 어떻게 해결할 수 있을까요?
  - IPv4와 IPv6의 차이에 대해 설명해 주세요.
  - 수많은 사람들이 유동 IP를 사용하고 있지만, 수많은 공유기에서는 고정 주소를 제공하는 기능이 이미 존재합니다. 어떻게 가능한 걸까요?
  - IPv4를 사용하는 장비와 IPv6를 사용하는 같은 네트워크 내에서 통신이 가능한가요? 가능하다면 어떤 방법을 사용하나요?
  - IP가 송신자와 수신자를 정확하게 전송되는 것을 보장해 주나요?
  - IPv4에서 수행하는 Checksum과 TCP에서 수행하는 Checksum은 어떤 차이가 있나요?
  - TTL(Hop Limit)이란 무엇인가요?
  - IP 주소와 MAC 주소의 차이에 대해 설명해 주세요.

  ---
</details>
<details>
  <summary><b>서브넷 마스크와, 게이트웨이에 대해 설명해 주세요.</b></summary>

  ---

  - NAT에 대해 설명해 주세요.
  - 서브넷 마스크의 표현 방식에 대해 설명해 주세요.
  - 그렇다면, 255.0.255.0 같은 꼴의 서브넷 마스크도 가능한가요?

  ---
</details>

## HTTP/S

<details>
  <summary><b>HTTP에 대해 설명해 주세요.</b></summary>

  ---

  - 공개키와 대칭키에 대해 설명해 주세요.
  - 왜 HTTPS Handshake 과정에서는 인증서를 사용하는 것 일까요?
  - SSL과 TLS의 차이는 무엇인가요?

  ---
</details>
<details>
  <summary><b>Stateless와 Connectionless에 대해 설명해 주세요.</b></summary>

  ---

- 왜 HTTP는 Stateless 구조를 채택하고 있을까요?
- Connectionless의 논리대로면 성능이 되게 좋지 않을 것으로 보이는데, 해결 방법이 있을까요?
- TCP의 keep-alive와 HTTP의 keep-alive의 차이는 무엇인가요?

  ---
</details>
<details>
  <summary><b>HTTP 응답코드에 대해 설명해 주세요.</b></summary>

  ---

  - 401 (Unauthorized) 와 403 (Forbidden)은 의미적으로 어떤 차이가 있나요?
  - 200 (ok) 와 201 (created) 의 차이에 대해 설명해 주세요.
  - 필요하다면 저희가 직접 응답코드를 정의해서 사용할 수 있을까요? 예를 들어 285번 처럼요.

  ---
</details>
<details>
  <summary><b>HTTP Method 에 대해 설명해 주세요.</b></summary>

  ---

  - HTTP Method의 멱등성에 대해 설명해 주세요.
  - GET과 POST의 차이는 무엇인가요?
  - POST와 PUT, PATCH의 차이는 무엇인가요?
  - HTTP 1.1 이후로, GET에도 Body에 데이터를 실을 수 있게 되었습니다. 그럼에도 불구하고 왜 아직도 이런 방식을 지양하는 것일까요?

  ---
</details>
<details>
  <summary><b>HTTP/1.1과 HTTP/2의 차이점은 무엇인가요?</b></summary>

---

  - HOL Blocking 에 대해 설명해 주세요.
  - HTTP/3.0의 주요 특징에 대해 설명해 주세요.

---
</details>

## 쿠키 & 세션 & 토큰
<details>
  <summary><b>쿠키와 세션의 차이에 대해 설명해 주세요.</b></summary>

  ---

  - 세션 방식의 로그인 과정에 대해 설명해 주세요.
  - HTTP의 특성인 Stateless에 대해 설명해 주세요.
  - Stateless의 의미를 살펴보면, 세션은 적절하지 않은 인증 방법 아닌가요?
  - 규모가 커져 서버가 여러 개가 된다면, 세션을 어떻게 관리할 수 있을까요?

  ---
</details>
<details>
  <summary><b>XSS에 대해서 설명해 주세요.</b></summary>

  ---

  - CSRF랑 XSS는 어떤 차이가 있나요?
  - XSS는 프론트엔드에서만 막을 수 있나요?

  ---
</details>

## DNS & Web Server & WAS

<details>
  <summary><b>DNS에 대해 설명해 주세요.</b></summary>

  ---

  - DNS는 몇 계층 프로토콜인가요?
  - UDP와 TCP 중 어떤 것을 사용하나요?
  - DNS Recursive Query, Iterative Query가 무엇인가요?
  - DNS 쿼리 과정에서 손실이 발생한다면, 어떻게 처리하나요?
  - 캐싱된 DNS 쿼리가 잘못 될 수도 있습니다. 이 경우, 어떻게 에러를 보정할 수 있나요?
  - DNS 레코드 타입 중 A, CNAME, AAAA의 차이에 대해서 설명해주세요.
  - hosts 파일은 어떤 역할을 하나요? DNS와 비교하였을 때 어떤 것이 우선순위가 더 높나요?

  ---
</details>
<details>
  <summary><b>www.github.com을 브라우저에 입력하고 엔터를 쳤을 때, 네트워크 상 어떤 일이 일어나는지 최대한 자세하게 설명해 주세요.</b></summary>

  ---

  - DNS 쿼리를 통해 얻어진 IP는 어디를 가리키고 있나요?
  - Web Server와 Web Application Server의 차이에 대해 설명해 주세요.
  - URL, URI, URN은 어떤 차이가 있나요?

  ---
</details>
<details>
  <summary><b>SOP 정책에 대해 설명해 주세요.</b></summary>

  ---

  - CORS 정책이 무엇인가요?
  - Preflight에 대해 설명해 주세요.

  ---
</details>

## 기타
<details>
  <summary><b>웹소켓과 소켓 통신의 차이에 대해 설명해 주세요.</b></summary>

  ---

- 소켓과 포트의 차이가 무엇인가요?
- 여러 소켓이 있다고 할 때, 그 소켓의 포트 번호는 모두 다른가요?
- 사용자의 요청이 무수히 많아지면, 소켓도 무수히 생성되나요?

  ---
</details>
<details>
  <summary><b>DHCP가 무엇인지 설명해 주세요.</b></summary>

  ---

- DHCP는 몇 계층 프로토콜인가요?
- DHCP는 어떻게 동작하나요?
- DHCP에서 UDP를 사용하는 이유가 무엇인가요?
- DHCP에서, IP 주소 말고 추가로 제공해주는 정보가 있나요?
- DHCP의 유효기간은 얼마나 긴가요?

  ---
</details>
<details>
  <summary><b>라우터 내의 포워딩 과정에 대해 설명해 주세요.</b></summary>

  ---

- 라우팅과 포워딩의 차이는 무엇인가요?
- 라우팅 알고리즘에 대해 설명해 주세요.
- 포워딩 테이블의 구조에 대해 설명해 주세요.

  ---
</details>
<details>
  <summary><b>로드밸런서가 무엇인가요?</b></summary>

  ---

- L4 로드밸런서와, L7 로드밸런서의 차이에 대해 설명해 주세요.
- 로드밸런서 알고리즘에 대해 설명해 주세요.
- 로드밸런싱 대상이 되는 장치중 일부 장치가 문제가 생겨 접속이 불가능하다고 가정해 봅시다. 이 경우, 로드밸런서가 해당 장비로 요청을 보내지 않도록 하려면 어떻게 해야 할까요?
- 로드밸런서 장치를 사용하지 않고, DNS를 활용해서 유사하게 로드밸런싱을 하는 방법에 대해 설명해 주세요.

  ---
</details>
<details>
  <summary><b>멀티플렉싱과 디멀티플렉싱에 대해 설명해 주세요.</b></summary>

  ---

- 디멀티플렉싱의 과정에 대해 설명해 주세요.

  ---
</details>

## Reference

- [큰돌 - CS 지식의 정석](https://www.inflearn.com/course/%EA%B0%9C%EB%B0%9C%EC%9E%90-%EB%A9%B4%EC%A0%91-cs-%ED%8A%B9%EA%B0%95)
- [WeareSoft](https://github.com/WeareSoft/tech-interview/blob/master/contents/network.md#questiontcp-%EA%B4%80%EB%A0%A8-%EC%A7%88%EB%AC%B8-1)
- [Gyoogle](https://gyoogle.dev/blog/computer-science/network/OSI%207%EA%B3%84%EC%B8%B5.html)
