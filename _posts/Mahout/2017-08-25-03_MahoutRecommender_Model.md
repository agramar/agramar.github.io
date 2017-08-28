---
layout: post
title: 03 Mahout 추천기 모델
category: Mahout
tags:
- Mahout
- Recommender Model
---

## 1. GenericUserBasedRecommender

## 2. GenericItemBasedRecommender

## 3. GenericBooleanPrefUserBasedRecommender

## 4. GenericBooleanPrefItemBasedRecommender

## 5. SVDRecommender (특이값 분해 기반 추천기)

## 6. RandomRecommender (랜덤 추천기)

## 7. CooccurenceRecommender

## 8. ALS-WR Recommender


수집 가능한 정보
- 평점
- 구매 이력
- 즐겨 찾기
- 조회 이력 : 전체, 최근

도메인 특화정보
- 사용자 정보 : 연령, 성별, 거주지, 직업
- 호텔 정보 : 유형, 가격대, 위치
- 시간 정보 : 

정보들을 통해 적절한 추천 모델을 만들어 개인화 추천을 해주어야함

이슈
- Cold Start 전략
- 익명의 사용자 처리
- 아키텍쳐