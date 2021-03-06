---
layout: post
title: 04 Spark 개발 프로세스
category: Spark
tags:
- Spark
- Development
---
# 1. 공통 개발 프로세스
1. SparkContext생성
    - 애플리케이션과 스파크클러스터와의 연결을 담당하는 객체
    - 스파크 애플리케이션을 수행하는데 필요한 각종 설정 정보를 담는 SparkConf를 SparkContext 생성자으 인자로 전달해야함
2. RDD 생성
    - 데이터를 처리하기 위한 클래스
    - 생성 방법
        1. 외부 데이터 소스
        2. 기존 RDD
3. RDD 처리
4. 결과 파일 처리
    - 처리 결과 저장
5. SparkContext종료

# 2. 언어별 프로세스
## Scala
* 프로세스
    1. 공통 개발 프로세스에 따른 코드 작성
    2. 단위 테스트
        - JUnit 단위 테스트(TDD)
        - FlatSpec(시나리오 명세, BDD)
    3. 소스코드 실행
        - Jar 파일 형태로 빌드한 뒤 실행(Maven)
        - SBT를 이용한 빌드
        
* 스칼라의 경우 Shell에서 PERL방식의 개발환경 제공 : 간단한 분석 처리를 위한 용도
    
## Python
* 프로세스
    1. 공통 개발 프로세스에 따른 코드 작성
    2. 단위 테스트
        - Python unit-test
    3. 소스코드 실행
        - 소스코드 실행

## Java
* 프로세스
    1. 공통 개발 프로세스에 따른 코드 작성
    2. 단위 테스트
        - JUnit 단위테스트
    3. 소스코드 실행
        - Jar 파일 형태로 빌드한 뒤 실행(Maven)
        
 # 3. 실행 스크립트 spark-submit
 - 애플리케이션을 실제 스파크 클러스터에서 쉽게 실행할 수 있게 스파크에서 기본적으로 제공하는 스크립트
 - --class  : 실행할 클래스의 경로를 지정하는 매개변수
 - local[*] : 애플리케이션에 전달되는 인자
 - 실행 스크립트 예 :

 ```
 > spark-submit --class [실행할 클래스 경로] [실행할 JAR파일 경로] local[스레드 개수] [실행할 클래스에 들어가는 매개변수1] [실행할 클래스에 들어가는 매개변수2] ... 
 ```

 
 # 4. spark-shell 에서 실행

# References
- [빅데이터 분석을위한 스파크2 프로그래밍(백성민, 위키북스, 2017)](http://wikibook.co.kr/spark/)
