# Hibernate

## 1. Hibernate 란?
- Java기반의 ORM(Object Relation Mapping) 프레임워크

## 2. ORM과 ODM

## 3. Annotation
### 1. @Entity
- 매핑할 클래스에 선언
- @Table로 따로 테이블 명을 지정하지 않으면 클래스명과 동일한 테이블과 매핑

### 2. @Table
- 클래스가 지정한 테이블 명으로 매핑

### 3. @Id
- 테이블에서 Identity 키로 사용할 필드를 지정

### 4. @Column
- 필드와 컬럼을 매핑

### 5. @Comment
- 주석

### 6. @DynamicInsert, @DynamicUpdate
- Null이 아닌 필드에 대해서만 Insert, Update 수행 하도록 설정
- 되도록 사용하도록 권장

### 7. @JoinTable, @JoinColumn, @ManyToMany, @ManyToOne
- 다른 Entity 클래스와 조인할때 사용