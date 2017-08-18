---
layout: post
title: 09 Spark Data Models
category: Spark
tags:
- Spark
- RDD
- DataFrame
- DataSet
---
## 1. 공통 특성

### 1.1. Transformation API
- 데이터를 가공해서 동일한 데이터 타입으로 반환하는 연산

### 1.2. Action API
- 데이터를 가공해서 가공한 데이터와 다른 데이터 타입으로 반환하는 연산

### 1.3. 불변성
- Transformation을 수행한다고 해서 기존의 데이터가 변하는게 아니고 기존의 데이터는 남아있고 새로운 데이터를 생성

### 1.4. 지연 동작
- Action 연산이 호출되기 전까지 Transformation 연산은 실제로 수행되지 않음

### 1.5. 데이터 프로세스
![AltText](/public/img/Spark/sparkRDD.png)


## 2. 스파크 데이터 모델 종류
![AltText](/public/img/Spark/rdd_df_ds.png)
### 2.1. RDD

#### 2.1.1. 특징
- Spark 0.5 부터 존재
- Spark Context로부터 생성

#### 2.1.2. 장점
- 함수형 프로그래밍
- 타입 안전성

#### 2.1.3. 한계
- 스키마에 대해서 표현할 방법이 없음

### 2.2. DataFrame

#### 2.2.1. 특징
- Spark 1.3 부터 존재
- 현재는 2.0부터 DataSet에서 흡수, 하위 호환성을 위해 API는 남아있음
- Spark Session로부터 생성

#### 2.2.2. 장점
- 스키마가 포함된 관계형 모델(SQL을 이용한 데이터 처리)
- RDD에 비해 성능상의 이점이 있음(처리 속도, 사용 메모리)

#### 2.2.3. 한계
- Compile Time에서 타입 안전성을 보장하지 않음

### 2.3. DataSet

#### 2.3.1. 특징
- Spark 1.6 부터 존재
- DataFrame과 RDD의 장점을 모아놓은 상위호환

#### 2.3.2. 장점
- RDD와 DataFrame이 제공하는 대부분의 기능 지원

#### 2.3.3. 단점
- 처리해야할 작업의 특성에 따라 RDD연산에 비해 복잡한 코드를 작성해야 하는 경우가 존재
- 아직 Scala와 Java만 API 지원

### 2.4. 비교
구분| RDD|DataFrame|DataSet
성능|비교적 느림|빠름|빠름
메모리 관리|누수 존재|최적화|최적화
Type-safety|보장|보장되지않음|보장
분석확장성|유연함|제한적|유연함

## 3. 결론
- RDD, DataFrame, DataSet에 대한 내용은 알아두어야 겠지만 결국은 실제 개발 단계에서는 DataSet을 사용하는 편이 좋음

## References
- 빅데이터 분석을 위한 스파크2 프로그래밍
- https://www.slideshare.net/KangDognhyun/apache-spark-70360736
