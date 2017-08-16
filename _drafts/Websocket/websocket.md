Websocket
=========

### Websocket이란?
- Transport protocol의 일종으로 웹버전의 TCP 또는 Socket
- 서버와 클라이언트 간에 양방향 통신 또는 데이터 전송이 가능하도록 하는 기술
- 2008년 HTML5에 포함이 되어서 프로토콜이 제정
- 실시간 상호작용 웹 애플리케이션 구현을 위해 사용 

### 작동원리
![Alt text](websocketprocess.png)
- 우선 서버와 클라이언트 간의 WebSocket 연결은 HTTP프로토콜을 통해 이루어짐(handshaking)
- Handshaking이 성공하면 HTTP를 WS 프로토콜로 바꾸는 과정을 진행 
- 그 이후 HTTP 연결은 자동으로 끊어짐

### 기존 Polling방식과의 차이
![Alt text](websocketvspolling.png)

### Websocket이 필요한 경우
1. 실시간 알림
2. 채팅
3. 공동 문서 작성
4. 데이터 분석(실시간 차트)

### Websocket Issues
- 미지원 브라우저
![Alt text](websocket.png)
- IE구버전이나 안드로이드 브라우저 구버전, Opera Mini등은 미지원

### 이슈에 대한 해결책
1. Spring Websocket : sockJS
2. Node.js : socketIO

### References
http://www.websocket.org/