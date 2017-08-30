---
layout: post
title: 02 TripAdvisor API ContentAPI
category: TripAdvisor
tags:
- TripAdvisor
- API
- Content API
---
# 1. Content API 제공 정보
- API KEY 신청 URL : [https://www.tripadvisor.com/APIAccessSupport](https://www.tripadvisor.com/APIAccessSupport)
- 기본적으로 호텔, 식당, 명소에 대한 정보를 함께 제공
- 제공 상세 정보들
    - Location ID, name, address, latitude, longitude
    - Read reviews link, Write a review link
    - 전체 평점, 순위, 상세 평점, 수상 이력, 리뷰 개수, 평점 이미지
    - 가격대 마크, 숙박 시설 카테고리 & 상세 카테고리
- 개발 프로세스
    1. 개발용 API 신청(심사 후 승인, 서비스 URL 필요)
    2. 승인
    3. 개발용 API_KEY 제공
    4. 개발
    5. 서비스 런치 신청
    6. 운영용 API_KEY 제공 

# 2. 화면에 표시해야 하는 사항
- 무료로 API를 사용하는 댓가로 TripAdvisor에서 요구 하는 링크와 로고를 보여주어야함.

# 3. Technical Overview
- 개발용 API KEY 제공 (초당 요청 30회, 일간 요청 1,000회 제한)
- 개발완료후 서비스 승인이 되면 운영용 API KEY로 전환(일간 요청 10,000회 제한)
- TripAdvisor에서는 API 응답 결과를 24시간동안 캐싱할 것을 추천함(파라미터로 자동 캐싱 키 제공)
- API KEY 보안에 각별히 신경 쓸것 (특히 클라이언트 단에서 요청 할때)
- Response Data Type : JSON

# 4. Content API 목록
- Request URL Example : http://api.tripadvisor.com/api/partner/2.0/location/155507?key="API KEY"

- 제공 API

|구분               |Parameter                 |Reponse|
|:-----------------:|:------------------------:|:-----------:|
|/location          | TripAdvisor location ID  | 장소이름, 주소, 평점, 리뷰갯수, 리뷰 조회 링크, 리뷰 작성 링크, 그밖의 정보| 
|/location_mapper   | 위도, 경도, (장소이름)   | TripAdvisor location ID |

- location_mapper를 통해 해당 장소에 대한 location ID를 얻어온 후에 location을 통해 정보를 조회

# 5. Content API 응답 데이터

## 5.1. [Business Content](https://developer-tripadvisor.com/content-api/business-content/)
1. 설명
    
    - POI(Points of Interest : 호텔, 식당, 관광지)에 대한 정보
    
2. 응답 데이터 목록
    
    - 기본 데이터
    
    | 항목               | 설명                 |
    |:-----------------:|:------------------------|
    | location_id | 장소 고유 ID |
    | name | 장소명 |
    | location_string | 지역명 |
    | num_reviews | 리뷰 개수 |
    | photo_count | 사진 개수 |
    | price_level | 통화 단위 |
        
    - Address and Geocoding(주소 및 좌표)
    
    | 항목               | 설명                 |
    |:-----------------:|:------------------------|
    | address_obj | 주소, 우편번호 |
    | logitude | 경도 |
    | latitude | 위도 |
    | ancestors | 상위 주소(도시, 주, 국가) |
    
    - Popularity Ranking(지역 평점 랭킹)
    
    | 항목               | 설명                 |
    |:-----------------:|:------------------------|
    | raking_data | 지역 평점 랭킹 정보 |
        
    - Bubble Ratings & Percent Recommended(총 평점 및 평점 이미지)
    
    | 항목               | 설명                 |
    |:-----------------:|:------------------------|
    | rating_image_url | 전체 평점 이미지 URL |
    | rating | 전체 평점 |
    
    - Subratings(항목별 평점)
        - 위치, 숙박, 방, 서비스, 가치, 청결도
    
    - Review Count and Breakdowns(리뷰 평점 분포도, 태그 정보 분포도)
    
    | 항목               | 설명                 |
    |:-----------------:|:------------------------|
    | review_rating_count | 리뷰 평점 분포도 |
    | trip_type | 태그 정보 분포도 |
    
    - Category, Subcategories, Groups, and Types
    
    | 항목               | 설명                 |
    |:-----------------:|:------------------------|
    | category | 큰 카테고리(hotel) |
    | subcategory | 세부 카테고리(b&b) |
        
    - Cuisines(식당 카테고리만 해당)
    
    - Award Content
    
    | 항목               | 설명                 |
    |:-----------------:|:------------------------|
    | awards | 수상 항목 표시 |
    
    - Links to TripAdvisor(TripAdvisor 링크)
    
    | 항목               | 설명                 |
    |:-----------------:|:------------------------|
    | web_url | 트립어드바이저 해당 장소 링크 |
    | write_review | 리뷰 작성 링크 |
    | see_all_photos | 사진 링크 |
    
    - Images
        - 트립 어드바이저 평점 이미지 

## 5.2. [Destination Content](https://developer-tripadvisor.com/content-api/destination-content/)
- 설명
    - 지역에 관한 정보
    
- 데이터 목록
    - 기본 데이터
    
    | 항목               | 설명                 |
    |:-----------------:|:------------------------|
    | location_id | 지역 고유 ID |
    | name | 지역명 |
    | abbrv | 지역명 약어 |
    | location_string | 일반적으로 쓰는 지역명 |
        
    - Address and Geocoding
    
    | 항목               | 설명                 |
    |:-----------------:|:------------------------|
    | address_obj | 주소, 우편번호 |
    | logitude | 경도 |
    | latitude | 위도 |
    | ancestors | 상위 주소(도시, 주, 국가) |
    
    - Category Counts
    
    | 항목               | 설명                 |
    |:-----------------:|:------------------------|
    | category_counts | 지역이 포함된 호텔, 식당, 명소 카운트 |
    
    - Categories, Subcategories, and Types
    
    | 항목               | 설명                 |
    |:-----------------:|:------------------------|
    | category | 큰 카테고리(geographic) |
    | subcategory | 세부 카테고리(city) |
    | geo_type | narrow, broad, hybrid |
    
    - Award Content
    
    | 항목               | 설명                 |
    |:-----------------:|:------------------------|
    | awards | 수상 항목 표시 |
    
    - Links to TripAdvisor(TripAdvisor 링크)
    
    | 항목               | 설명                 |
    |:-----------------:|:------------------------|
    | web_url | 트립어드바이저 해당 장소 링크 |
    | see_all_photos | 사진 링크 |
    | see_all_restaurants | 지역 식당 링크 |
    | see_all_attractions | 지역 명소 링크 |
    | see_all_hotels | 지역 호텔 링크 |

# 6. 지원 언어
- [https://developer-tripadvisor.com/content-api/supported-languages/](https://developer-tripadvisor.com/content-api/supported-languages/)
