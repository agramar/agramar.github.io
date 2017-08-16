---
layout: post
title: Spark 설치
category: Spark
tag: Spark
---

## 1. 실행환경
- OS : **UNIX-like systems(Linux, Mac OS)**, Windows
- 언어 : **Java8+**, Python 2.7+/3.4+, Scala 2.11.x

## 2. 실행환경 설치
#### Linux (Ubuntu 16.04 LTS)
1. **설치과정에서 필요한 공통 소프트웨어 설치[필수]**
    ````
    # apt-get update
    # apt-get install software-properties-common
    ````

2. **JAVA 설치[필수]**
    ````
    # add-apt-repository ppa:webupd8team/java
    # apt-get update
    # apt-get install oracle-java8-installer
    # java -version
    # javac -version
    ````

3. **Spark 설치[필수]**
    ````
    # cd /usr/local/src/
    # wget https://d3kbcqa49mib13.cloudfront.net/spark-2.2.0-bin-hadoop2.7.tgz
    # tar xvf spark-2.2.0-bin-hadoop2.7.tgz
    # cd spark-2.2.0-bin-hadoop2.7
    ````

4. **Spark 환경변수 설정[필수]**
    - 환경변수 설정파일 열기
    ````
    # vim ~/.bashrc
    ````
    - 문서 하단에 추가 후 저장
    ````
    export SPARK_HOME=/usr/local/src/spark-2.2.0-bin-hadoop2.7
    export PATH=$SPARK_HOME/bin:$PATH
    ````
    - 추가된 환경변수 적용
    ````
    # source ~/.bashrc
    ````

5. Hadoop 환경 설정


#### Windows 10
- [필수]Java 설치
    1. Java 설치
    2. 환경변수 설정

- [선택]Scala 설치
    1. Scala 다운로드 및 설치
        - 다운로드
    2. 환경변수 설정
        ````
        SCALA_HOME  :
        Path        : %SCALA_HOME%\bin
        ````

- [선택]Python 설치
    1. Python 2.7 / 3.5+ 설치
        - 다운로드
    2. 환경변수 설정
        - 환경변수 설정

- [필수]스파크 설치
    1. 스파크 다운로드
        - https://d3kbcqa49mib13.cloudfront.net/spark-2.2.0-bin-hadoop2.7.tgz
    2. 스파크 설치
        - C:\spark 경로에 다운받은 파일 스파크 파일 복사
        - 압축풀기 tgz -> tar -> 폴더이름으로 압축 풀기
        - C:\spark\spark-2.2.0-bin-hadoop2.7 경로에 압축이 풀렸는지 확인
    3. 환경변수 설정
        ````
        SPARK_HOME  : C:\spark\spark-2.2.0-bin-hadoop2.7
        Path        : %SPARK_HOME%\bin
        ````
- [필수]Hadoop Windows Utilities 설치
    1. 다운로드
        - Hadoop Winutilities   : https://github.com/steveloughran/winutils/raw/master/hadoop-2.7.1/bin/winutils.exe
        - Hadoop Binary         :
    2. 다운받은 Hadoop 유틸 파일 복사
        - C:\spark\spark-2.2.0-bin-hadoop2.7\bin 경로에 복사
    3. Hadoop 환경변수 설정
        ````
        HADOOP_HOME : C:\spark\spark-2.2.0-bin-hadoop2.7
        Path        : %HADOOP_HOME%\bin
        ````
    4. tmp/hive 폴더 권한 설정[권한 오류 발생시]
        ````
        > %SPARK_HOME%\bin\winutils.exe chmod 777 \tmp\hive
        ````

#### Mac OS

## 3. 개발 환경 설치
- 선행조건 : 실행환경 설치

#### Windows 10
- Scala
    1. Scala-IDE 설치
    2. SBT 설치

- Python
    1. PyCharm 설치

- Java
    1. Eclipse 설치
    2. Maven 설치

#### Linux

#### MacOS

## 4. 실행 확인
    ````
    # spark-shell
    ````
    - 오류 로그없이 실행되면 정상 실행된 것임

#### References
- 빅데이터 분석을 위한 스파크2 프로그래밍
- [Apache Spark installation on Windows 10](https://hernandezpaul.wordpress.com/2016/01/24/apache-spark-installation-on-windows-10/)
