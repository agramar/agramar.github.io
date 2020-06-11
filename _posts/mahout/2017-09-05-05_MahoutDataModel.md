---
layout: post
title: 05 Mahout 데이터 모델
category: Mahout
tags:
- Mahout
- Recommender
- Data Model
---
## 1. File Data Model

### 데이터 불러오기


### 데이터 갱신
#### 새로고침
- 메인 데이터 파일이 갱신하고 새로고침을 하면 파일 전체를 새로 읽음

#### 파일업데이트
- 변경된 부분만 처리
- 메인 데이터 파일과 같은 디렉터리에 위치하고 점이 나오기전까지 같은 접두사인 파일이 있을경우
    - 메인 데이터 파일 : data.csv
    - 업데이트 데이터 파일 : data.1.csv 

- 선호 추가 혹은 변경

```
userId, itemId, pref
```

- 기존 선호 삭제

```
userId, itemId,
```

## 2. Database Data Model

### RDBMS
- MySQL, PostgreSQL
- File Data Model에 비해 현저히 느림


#### JNDI를 이용한 설정

```XML
<Resource 
    name="jdbc/taste"
    auth="Container"
    type="javax.sql.DataSource"
    username="user"
    password="password"
    driverClassName="com.mysql.jdbc.Driver"
    url="jdbc:mysql://localhost:3306/mydatabase"
/>
```

#### DataSource Library를 이용한 설정

```java
MysqlDataSource dataSource = new MysqlDataSource();
dataSource.setServerName("database_host");
dataSource.setUser("user");
dataSource.setPassword("password");
dataSource.setDatabaseName("database_name");

JDBCDataModel dataModel = new MySQLJDBCDataModel(dataSource, "pref_table", "user_column", "item_column", "pref_column"); 
```

#### DB 설정 및 최적화
- 스키마 : userid(bigint), itemid(bigint), rating(float), timestamp(timestamp)
- userid, itemid 컬럼은 indexing 되어 있어야 하고 PK여야 한다
- MySQL Connector/J 드라이버를 사용할 경우 cachePrepareStatements를 TRUE로 설정
- 버퍼와 쿼리캐시를 튜닝


### NoSQL DBMS
- MongoDB