# Table Partitioning

### 개념
- 논리적으로 묶여있는 하나의 테이블을 물리적으로 여러개의 테이블로 분리

### 이유
- 대용량 데이터 처리 테이블의 성능 저하를 막기 위해

### 종류
- Range Partition : Column Value의 범위에 따라 파티셔닝

- List Partition : Column Value에 따라 파티셔닝

- Hash Partition : 지정된 Hash Condition에 따라 파티셔닝

- Composite Partition : 복합 파티셔닝
