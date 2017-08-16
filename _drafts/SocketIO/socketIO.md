SocketIO
========

### SocketIO란?
- WebSocket을 기반으로 FlashSocket, AJAX Long Polling등 다양한 방식의 실시간 웹 기술들을 하나의 API로 추상화한 node.js모듈(MIT 라이센스 오픈소스)

### 동작 방식
![Alt text](socketIO.png)

### 장점
- 브라우저와 웹 서버의 종류와 버전을 파악하여 가장 적합한 기술을 선택하여 사용하는 방식이기 때문에 브라우저의 종류와 상관없이 실시간 웹 구현 가능
      
### 단점
- node.js 모듈이기 때문에 javascipt외에 다른 언어에서는 사용할 수 없음

### 활용 예
- 실시간 웹 푸시알림 서비스
- 실시간 채팅 서비스
- 실시간 공동 문서 작성 서비스
- 실시간 데이터 분석(실시간 차트)

#### TODO
- SocketIO를 활용한 실시간 채팅 구현
- SocketIO를 활용한 실시간 알림 구현

### References
https://socket.io/