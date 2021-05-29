---
layout: post
title: 스프링 배치 완벽 가이드 2/e
category: Book
tags:
- Spring Batch
- Spring
- Batch
- Book
---

스프링 배치 완벽 가이드 2/e(Definitive Guide to Spring Batch. Second Edition)
=================

# 1장 배치와 스프링

## 1.1. 배치 처리의 역사
## 1.2. 배치가 직면한 과제
## 1.3. 왜 자바로 배치를 처리하는가?
## 1.4. 스프링배치의 기타 사용 사례
## 1.5. 스프링 배치 프레임워크
## 1.6. 이 책의 진행 방식


# 2장 스프링 배치

## 2.1. 배치 아키텍처
## 2.2. 프로젝트 초기 설정
## 2.3. Hello, World! 법칙
## 2.4. 잡 실행하기


# 3장 예제 잡 애플리케이션

## 3.1. 애자일 개발 이해하기
## 3.2. 은행 거래명세서 잡의 요구 사항 이해하기
## 3.3. 배치 잡 설계하기


# 4장 Job 과 Step 이해하기

## 4.1. Job 소개하기
### Job 생명주기 따라가보기

## 4.2. Job 구성하기
### Job 기본 구성
### JobParameter
### JobListener 적용하기
### ExecutionContext
### ExecutionContext 조작하기

## 4.3. Step 알아보기
### Tasklet 처리와 Chunk 처리 비교
### Step 구성
### 그 밖의 여러 다른 유형의 Tasklet 이해하기
### Step Flow


## 5장 JobRepository 와 메타데이터

## 5.1. JobRepository 란?
### RDB JobRepository
### InMemory JobRepository

## 5.2. 배치 인프라스트럭처 구성하기
### BatchConfigurer Interface
### Customizing JobRepository
### Customizing TransactionManager
### Customizing JobExplorer
### Customizing JobLauncher
### 데이터베이스 구성하기

## 5.3. 잡 메타데이터 사용하기
### JobExplorer


## 6장 잡 실행하기

## 6.1. 스프링 부트로 배치 잡 실행하기

## 6.2. REST 방식으로 잡 실행하기
### 쿼츠를 사용해 스케줄링 하기

## 6.3. 잡 중지하기
### 자연스러운 완료
### 프로그래밍적으로 중지하기
### 오류 처리

## 6.4. 재시작 제어하기
### 잡의 재시작 방지하기
### 재시작 횟수를 제한하도록 구성하기
### 완료된 스텝 재실행하기


## 7장 ItemReader

## 7.1. ItemReader Interface

## 7.2. File
### CSV
- FlatFileItemReader
- MultiResourceItemReader

### XML
- StaxEventItemReader

### JSON
- JsonItemReader

## 7.3. DB
### JDBC
- JdbcCursorItemReader
- JdbcPagingItemReader

### Hibernate
- HibernateCursorItemReader
- HibernatePagingItemReader

### JPA
- JpaPagingItemReader

### Stored Procedure
- StoredProcedureItemReader

### Spring Data
- MongoItemReader
- RepositoryItemReader

## 7.4. 기존 서비스
### ItemReaderAdapter

## 7.5. CustomItemReader
### Implement ItemReader Interface
### Implement ItemStream Interface

## 7.6. 에러 처리
### 레코드 건너뛰기
### 잘못된 레코드 로그 남기기
### 입력이 없을 때의 처리


## 8장 ItemProcessor

### 8.1. ItemProcessor 소개

### 8.2. ItemProcessor 사용 하기
- ValidatingItemProcessor
- ItemProcessorAdapter
- ScriptItemProcessor
- CompositeItemProcessor

### 8.3. ItemProcessor 직접 만들기
- 아이템 필터링 하기


## 9장 ItemWriter

### 9.1. ItemWriter 소개

### 9.2. File ItemWriter
- FlatFileItemWriter
- StaxEventItemWriter

### 9.3. DB ItemWriter
- JdbcBatchItemWriter
- HibernateItemWriter
- JpaItemWriter

### 9.4. Spring Data ItemWriter
-

### 9.5. 그밖의 출력 방식을 위한 ItemWriter
- ItemWriterAdapter
- PropertyExtractingDelegatingItemWriter
- JmsItemWriter
- SimpleMailMessageItemWriter

### 9.6. 여러 자원을 사용하는 ItemWriter
- MultiResourceItemWriter
- CompositeItemWriter
- ClassifierCompositeItemWriter


## 10장 예제 애플리케이션

### 10.1. 거래명세서 잡 검토하기
### 10.2. 새 프로젝트 초기 구성하기
### 10.3. 갱신할 고객 정보 가져오기
### 10.4. 거래 정보 가져오기
### 10.5. 잔액에 거래 내역 적용하기
### 10.6. 월별 거래명세서 생성하기


## 11장 확장과 튜닝

### 11.1. 배치처리 프로파일링 하기
- 스프링 배치 애플리케이션 프로파일링 하기

### 11.2. 잡 확장하기
- 다중 스레드 스텝
- 병렬 스텝
- 병렬 스텝 구성하기
- AsyncItemProcessor 와 AsyncItemWriter
- 파티셔닝
- 원격청킹


## 12장 클라우드 네이티브 배치

### 12.1. 12요소 애플리케이션
- 코드베이스
- 의존성
- 구성
- 백엔드 서비스
- 빌드, 릴리스, 실행
- 프로세스
- 포트 바인딩
- 동시성
- 폐기 가능
- 개발/운영 환경 일치
- 로그
- 관리자 프로세스

### 12.2. 간단한 배치잡

### 12.3. 서킷 브레이커

### 12.4. 구성 외부화
- 스프링 클라우드 컨피그

### 12.5. 배치 처리 오케스트레이션
- 유레카를 사용한 서비스 바인딩


## 13장 배치 처리 테스트하기

### 13.1. Junit 과 Mockito 를 사용한 단위 테스트
- Junit
- Mock 객체
- Mockito

### 13.2. 스프링 클래스를 사용해 통합 테스트 하기
- 스프링을 사용해 통합 테스트하기
- 스프링 배치 테스트 하기


# 참고 사항
- https://github.com/Apress/def-guide-spring-batch
- https://github.com/AcornPublishing/definitive-spring-batch