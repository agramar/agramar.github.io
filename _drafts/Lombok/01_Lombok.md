# Lombok
## 1. Lombok 이란?
## 2. Lombok 설치

## 3. Lombok 어너테이션
#### 1. @Getter, @Setter
- getter, setter 함수 생성
- 접근 제한자 설정 가능
```java
@Getter(AccessLevel.PACKAGE)
```

#### 2. @EqualsAndHashCode
- equals, hashCode 함수 생성
- 특정 필드 제외가능
```java
@EqualsAndHashCode(exclude={"field1", "field2"})
```

#### 3. @ToString
- toString 함수 생성
- 특정 필드 제외 가능
```java
@ToString(excluded="feild")
```

#### 4. @Log
- logging을 위한 private static final Logger log 추가
- log.error(), log.warn(), log.debug(), log.info() 형태로 사용

#### 5. @AllArgsConstuctor, @RequiredArgsConstructor, @NoArgsConstructor
- 생성자 함수 생성

#### 6. @Data
- 모든 필드에 대한 getter, setter, toString, equals, hashCode 생성
- @NonNull로 명시된 필드에 대한 값을 파라미터로 받는 생성자 함수 생성

## 4. Lombok Document
 - Guide : https://projectlombok.org/features/
 - Official Document : https://projectlombok.org/api/overview-summary.html
