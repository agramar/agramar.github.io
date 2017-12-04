## 1. Api Spec
### 1. API Endponts
```
http[s]://{subdomain}.ean.com/ean-services/rs/hotel/v3/{request name}?&{request element 1}&{request element 2}&...
```
- Encoding : UTF-8

### 2. Usage Requirements
- Implement logic to prevent duplicate bookings
- Implement logic to handle pending and error states
- Determine valid payment types before booking
- Include the following with each booking request:
    - Customer's IP address
    - Customer's email address
    - Customer's browser user agent
    - Unique confirmation ID
    - Your company's internal booking reference
- Implement any anti-fraud tools as directed by Expedia Affiliate Network

### 3. Traffic Ratio Requiremetns
- We require our partners to maintain the following traffic ratios (for every x number of requests of the given type, we expect at least 1 booking at minimum):
    - Hotel List Requests: 5000:1
    - Room Availability Requests: 500:1

### 4. API Services
1. Hotel List(호텔 목록)
2. Room Availablitiy(이용 가능 객실 조회)
3. Book Reservation(객실 예약) : 8개 객실까지 예약 가능
4. Itinierary Retrieval
5. Cancel Reservation(객실 예약 취소)
6. Room Images(객실 사진)
7. Payment Types(결제 타입)
8. Hotel Info(호텔 정보)


## 2. B2B 요구사항
### 2.1. 일반
1. 제휴사는 호텔 공급사가 되어서는 안된다 : 호텔 공급만 받아야함
2. Expedia나 EAN의 로고를 사용하면 안된다.
3. 제휴사는 예약시 실제 예약자의 이름을 제공해야 한다.
4. EAN 예약 이용약관 링크를 제휴사 이용약관 안에 포함시켜야 함
5. EAN API에서 반환하는 가격 혹은 예약조건을 변경하지 않아야 함
6. Customer support numbers to be clearly displayed, including links to online customer service tools
7. 적절한 신용카드 규정을 표시하고 사용해야함
8. Evidence of PCI compliance supplied for applicable partners
9. 하위 제휴사도 EAN을 이용하려면 EAN의 이용약관에 동의해야함
10. TripAdvisor의 컨텐츠를 이용하려면 TripAdvisor의 가이드 라인을 따라야함

### 2.2. 검색 페이지
1. 객실 검색시에 아동/청소년 숫자와 각각의 나이를 입력할 수 있어야 함

### 2.3. 호텔 리스트 목록 페이지
1. 세금 및 수수료 내역이 제공되는 경우 개별 청구가 명확하게 표시되어야합니다

### 2.4. 이용가능한 호텔/객실
1. 세금 및 수수료들이 각 항목별로 명확하게 표시되어야 한다.
2. Sales tax values are reported separately when applicable
3. 객실 타입(Bed Type) 내역이 각각의 객실에 표시되어야 함
4. 체크인 안내사항이 표시되어야 함
5. 환불 불가 정책이 명확히 표시되야 함
6. 특별체크인안내사항이 표시되어야 함

### 2.5. 예약 페이지
1. 민감한 정보는 SSL 암호화가 적용되야 함
2. 상세한 요금 내역이 제공되어야 함
3. 세금 및 수수료 내역은 별도로 명확히 표시되어야 함
4. 최종 요금이 명확히 표시되야함
5. 제휴사의 예약 수수료가 별도로 명확히 표시되야 함
6. City/Mandatory tax values must be reported separately
7. Sales tax values are reported separately when applicable

### 2.6. 예약 확정 페이지

### 2.7. 예약 확정 이메일/바우처

### 2.8. Technical & Fraud 예방 요구사항
1. 제휴사는 각 예약 요청별로 Unique ID를 제출해야 함
2. 오류, 지연 처리 로직을 포함해야 함
3. 제휴사는 매 요청마다 고객의 IP주소를 제출해야 함
4. 각 요청마다 세션 ID를 제공해야 함
5. 

## 3. 연동 규격서
### 3.1. 개요
- 연동개발이 완료되면 EAN에 사이트 검토요청 필요
- 검토 뒤에 판매 액세스를 위해 CID와 API Key쌍을 활성화

- 호텔목록
```json
{
    Hotel List : [

    ]
}
```
- 예약 가능 객실
- 예약
- 일정 요청
- 객실 이미지
- 결제 유형 
- Ping 요청 : 응답시간 요청
- 지리 함수
- 대체 숙박업소
- 호텔 정보 : 단일 호텔에 대한 호텔 및 객실 편의시설, 숙박업소 정보, 공급업체, 숙박업소 이미지 반환
- 객실 침대 유형

### 3.2. 호텔 목록
- 호텔 목록 또는 특정 호텔을 검색

### 3.3. 예약 가능 객실
