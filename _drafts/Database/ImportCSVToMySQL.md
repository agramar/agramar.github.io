# CSV 파일 MySQL Import 방법

1. WorkBench
- 좀 느림 알아서

2. CL
- 개빠름
```
LOAD DATA LOCAL INFILE 'file_name'
INTO TABLE table_name
FIELDS TERMINATED BY ','
ENCLOSED BY '"'
LINES TERMINATED BY '\n'
(column1,column2,column3, ...);
```