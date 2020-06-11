---
layout: post
title: 01 TripAdvisor API 가이드
category: TripAdvisor
tags:
- TripAdvisor
- API
- Introduction
---
## 0. TripAdvisor란
- 세계 최대 여행 리뷰 사이트
- 호텔에 대한 기본적인 정보는 물론 신뢰도 높은 리뷰, 평점 데이터를 API를 통해 무료로 제공
- 정보제공은 무료인 대신에 필수 요구조건이 존재(실제 운영되는 서비스여야 하고, 트립어드바이저 로고 같은 출처 이미지를 표시해야함)
- TripAdvisor 이외에도 agoda, Booking.com, Expedia, Hotels.com 같은 글로벌 OTA 브랜드들도 동일한 서비스 제공
- 글로벌 OTA간에도 리뷰정보를 상호 공유(Hotels.com에 자체 리뷰정보와 TripAdvisor의 리뷰정보를 함께 제공)
 
## 1. 제공 API 종류
- 공식 Document URL : https://developer-tripadvisor.com/home/

### TripAdvisor Content API
- 공식 관광 웹사이트 및 TripAdvisor에 의해 승인된 파트너에게 Content API를 통해 호텔 정보 제공
- 이 콘텐츠는 개별 레이팅 점수를 대량으로 찾고있는 웹 사이트를 위한 것입니다

### TripConnect(Solutions for B2B Connectivity Partners)
- TripConnect는 호텔, 여관 및 B&Bs가 세계에서 가장 큰 여행 사이트에서 예약을 위해 경쟁 할 수있는 강력하고 흥미로운 새로운 방법입니다. 
- TripConnect는 숙박 시설 소유자가 웹 사이트의 예약 페이지로 직접 예약 할 준비가 된 방문자를 데려 와서 새로운 비즈니스를 창출하도록합니다.
- Connectivity 파트너는 숙박산업의 B2B 기술 솔루션 공급자입니다. 여기에는 중앙 예약 시스템, 부동산 관리 시스템, 채널 관리자 및 인터넷 예약 엔진이 포함됩니다.
- Connectivity partners are B2B technology solution providers to the Hotel and Hospitality Industry.  These include Central Reservation Systems, Property Management Systems, Channel Managers and Internet Booking Engines.
- 제공 API : Hotel Availability Check API, Instant Booking API, Review Express API, TripConnectCampaign Data API

### Self Implemented Partners
- TripAdvisor Self implemented product is committed to making the process of connecting to our Meta and Instant book system easy. This section is for OTAs, Hotel Chains and partners wanting to connect in to Tripadvisor's meta and instant booking platforms. The services offered here will allow you to self implement these APIs and be up and running in our environment quickly. If you are already connected in to our Meta API, congratulations you are already half way into becoming an instant book partner. If you are just getting started, follow the simple process along and our teams will provide assistance. For any questions please reach out to your account manager at TripAdvisor.
- TripAdvisor자체는 당사의 메타 및 InstantBook시스템에 연결하는 과정을 쉽게 수행할 수 있도록 해 줍니다. 이 섹션은 Tripadvisor의 메타 및 즉석 예약 플랫폼에 연결하고자 하는 OTA, 호텔 체인 및 파트너를 위한 것입니다. 여기서 제공되는 서비스를 통해 이러한 API를 구현하고 환경에서 신속하게 실행할 수 있습니다. 만약 당신이 이미 우리의 메타 API에 연결되어 있다면, 당신이 이미 책을 읽는 파트너가 되는 것이 이미 반쯤 되었다는 것을 축하합니다. 지금 막 시작하고 있다면 간단한 절차를 따르시고 저희 팀은 도움을 드릴 것입니다. 궁금하신 점은 TripAdvisor의 계정 매니저에게 문의하시기 바랍니다.
- 자신이 구현한 플랫폼에서 TripAdvisor의 호텔정보를 직접 예약할수 있는 방법을 제공하는 API
- 제공 API : Hotel Availability Check API, Instant Booking API


### References
- [http://www.olery.com/blog/the-best-travel-apis-discover-contribute/](http://www.olery.com/blog/the-best-travel-apis-discover-contribute/)
