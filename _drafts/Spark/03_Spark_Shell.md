# 스파크 셸(Spark Shell)
- 스파크 셸이란?
    - 정의

- 셸 실행
    ````
    # cd ${SPARK_HOME}
    # spark-shell
    ````

- Spark shell application UI
    - 셸을 실행시킨 상태로 브라우져로 4040포트로 접속하면 Spark shell application UI에 접속 가능
    

- 로그 설정 변경
    - 보다 상세한 로그 확인을 위해 로그레벨을 WARN에서 INFO로 변경
    ````
    # cd ${SPARK_HOME}/conf
    # cp ./log4j.properties.template log4j.properties
    # vim log4j.properties
    
    "log4j.logger.org.apache.spark.repl.Main=WARN" 을
    "log4j.logger.org.apache.spark.repl.Main=INFO" 로변경
    ````

- 스파크 셸에서 스파크 컨텍스트 확인
    ````
    # spark-shell
    scala> sc
    res0: org.apache.spark.SparkContext ...
    ````
    
- 단어 수 세기 예제를 스파크 셸을 이용해 실행
    ````
    # spark-shell
    
    scala> val file = sc.textFile("file:///usr/local/src/spark-2.2.0-bin-hadoop2.7/README.md")
    scala> val words = file.flatMap(_.split(" "))
    scala> val result = words.countByValue
    scala> result.get("For").get
    
    res1: Long = 3
    ````
    
- 스파크 셸 실행 옵션
    1. 스파크 셸이 동작할 떄 필요한 클래스와 라이브러리에 관한 옵션
    2. 애플리케이션 실행과 관련된 옵션
    3. 클러스터 동작과 관련된 옵션
        - 실행옵션을 통해 로컬/클러스터 등으로 선택해 구동 가능
     