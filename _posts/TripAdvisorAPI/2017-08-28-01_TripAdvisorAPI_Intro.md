# TripAdvisor API 가이드
- TripAdvisor란?
- 공식 Document URL : https://developer-tripadvisor.com/home/

## 1. 제공 API 종류

### TripAdvisor Content API
- 공식 관광 웹사이트 및 승인된 파트너에게 Content API를 통해 호텔 정보 제공
- 이 콘텐츠는 개별 레이팅 점수를 대량으로 찾고있는 웹 사이트를 위한 것입니다

### TripConnect(Solutions for B2B Connectivity Partners)
- TripConnect는 호텔, 여관 및 B & Bs가 세계에서 가장 큰 여행 사이트에서 예약을 위해 경쟁 할 수있는 강력하고 흥미로운 새로운 방법입니다. TripConnect는 숙박 시설 소유자가 웹 사이트의 예약 페이지로 직접 예약 할 준비가 된 방문자를 데려 와서 새로운 비즈니스를 창출하도록합니다.
- 연결 파트너는 Hotel and Hospitality Industry의 B2B 기술 솔루션 공급자입니다. 여기에는 중앙 예약 시스템, 부동산 관리 시스템, 채널 관리자 및 인터넷 예약 엔진이 포함됩니다.
- Connectivity partners are B2B technology solution providers to the Hotel and Hospitality Industry.  These include Central Reservation Systems, Property Management Systems, Channel Managers and Internet Booking Engines. 

### Self Implemented Partners
- 자신의 플랫폼에서 TripAdvisor의 호텔정보를 직접 예약할수 있는 방법을 제공하는 API
 
- TripAdvisor Self implemented product is committed to making the process of connecting to our Meta and Instant book system easy. This section is for OTAs, Hotel Chains and partners wanting to connect in to Tripadvisor's meta and instant booking platforms. The services offered here will allow you to self implement these APIs and be up and running in our environment quickly. If you are already connected in to our Meta API, congratulations you are already half way into becoming an instant book partner. If you are just getting started, follow the simple process along and our teams will provide assistance. For any questions please reach out to your account manager at TripAdvisor.

## 2. TripAdvisor Content API

### 2.1. Content API 제공 정보
- API KEY 신청 URL : 
- 기본적으로 호텔, 식당, 명소에 대한 정보를 함께 제공
- 제공 상세 정보들
    - Location ID, name, address, latitude, longitude
    - Read reviews link, Write a review link
    - 전체 평점, 순위, 상세 평점, 수상 이력, 리뷰 개수, 평점 이미지
    - 가격대 마크, 숙박 시설 카테고리 & 상세 카테고리

### 2.2. 화면에 표시해야 하는 사항
- 무료로 API를 사용하는 댓가로 TripAdvisor에서 요구 하는 링크와 로고를 보여주어야함.

### 2.3. Technical Overview
- 개발용 API KEY 제공 (초당 요청 30회, 일간 요청 1,000회 제한)
- 개발완료후 서비스 승인이 되면 운영용 API KEY로 전환(일간 요청 10,000회 제한)
- TripAdvisor에서는 API 응답 결과를 24시간동안 캐싱할 것을 추천함(파라미터로 자동 캐싱 키 제공)
- API KEY 보안에 각별히 신경 쓸것 (특히 클라이언트 단에서 요청 할때)
- Response Type : JSON

### 2.4. Content API 목록
- Request URL Example : http://api.tripadvisor.com/api/partner/2.0/location/155507?key="API KEY"

- 제공 API

|구분               |Parameter                 |Reponse|
|:-----------------:|:------------------------:|:-----------:|
|/location          | TripAdvisor location ID  | 장소이름, 주소, 평점, 리뷰갯수, 리뷰 조회 링크, 리뷰 작성 링크, 그밖의 정보| 
|/location_mapper   | 위도, 경도, (장소이름)   | TripAdvisor location ID |


### 2.5. Content API 응답 데이터

#### [Business Content](https://developer-tripadvisor.com/content-api/business-content/)
- 설명
    - 호텔, 식당, 관광지(POI) 등에 대한 정보
- 데이터 목록
    - Address and Geocoding
    - Popularity Ranking
    - Bubble Ratings & Percent Recommended
    - Subratings
    - Review Count and Breakdowns
    - Category, Subcategories, Groups, and Types
    - Cuisines
    - Award Content
    - Links to TripAdvisor
    - Images

#### [Destination Content](https://developer-tripadvisor.com/content-api/destination-content/)
- 설명
    - 지역에 관한 정보
- 데이터 목록
    - Address and Geocoding
    - Category Counts
    - Categories, Subcategories, and Types
    - Award Content
    - Links to TripAdvisor

### 2.6. 지원 언어
- [https://developer-tripadvisor.com/content-api/supported-languages/](https://developer-tripadvisor.com/content-api/supported-languages/)
