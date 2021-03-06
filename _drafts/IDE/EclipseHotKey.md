# 이클립스 유용한 단축키

## 소스 네비게이션
- Ctrl + 마우스커서(혹은 F3) : 클래스나 메소드 혹은 멤버를 상세하게 검색하고자 할때
- Alt + ->, Alt + <- : 이후, 이전
- F4 : 클래스 선택하고 누르면 해당 클래스의 구조를 볼수 있음
- Ctrl + O : 해당 소스의 메소드 리스트를 확인하려 할때

## 검색
- Ctrl + Shift + R : 파일명으로 검색해서 파일열기
- Ctrl + K : 찾고자 하는 문자열을 블럭으로 설정한 후 키를 누른다
- Ctrl + Shift + K : 역으로 찾고자 하는 문자열을 찾아감.
- Ctrl + J : 입력하면서 찾을 수 있음.
- Ctrl + Shift + J : 입력하면서 거꾸로 찾아갈 수 있음.
- Ctrl + F : 현재 파일에서 문자열 검색
- Ctrl + H : 전체 파일에서 문자열 검색
- Ctrl + Shift + G : 특정 메써드나 필드를 Reference하고 있는 곳을 찾는다.

## 소스 편집
- Ctrl + Shift + F : 코드 자동 정리
- Ctrl + 1 : Quick Fix. 에러가 발생했을 경우 Quick Fix를 통해 쉽게 해결이 가능하다.
- CTRL + L : 특정 줄번호로 가기
- Alt + Shift + J : 자동으로 주석 달기 (메소드나 멤버변수에 포커스 두고 실행)
- F2 : 컴파일 에러의 빨간줄에 커서를 가져다가 이 키를 누르면 에러의 원인에 대한 힌트를 제공한다.
- Ctrl + L : 원하는 소스 라인으로 이동
    - 로컬 히스토리 기능을 이용하면 이전에 편집했던 내용으로 변환이 가능하다.
- Ctrl + D : 한줄 삭제
- Ctrl + W : 파일 닫기 
- Ctrl + I : 들여쓰기 자동 수정 
- Ctrl + Shift + / : 블록 주석(/*..*/) 추가
- Ctrl + / : 해주면 여러줄이 한꺼번에 주석처리됨. 주석 해제하려면 반대로 하면 됨
- Alt + UP(DOWN) : 위(아래)줄과 바꾸기
- Alt + Shift + 방향키 : 블록 선택하기 
- Ctrl + Shift + Space : 메소드의 파라메터 목록 보기 
- Ctrl + Shift + F4 : 열린 파일 모두 닫기 
- Ctrl + M : 전체화면 토글
- Ctrl + , or . : 다음 annotation(에러, 워닝, 북마크 가능)으로 점프
- Ctrl + T : 계층구조 열기(인터페이스 구현클래스간 이동)

## 응용
- Alt + Shift + S : 각종 코드 제네레이터
    - O : constructor 생성
    - R : getter, setter 메소드 생성
    - S : toString 메소드 생성
