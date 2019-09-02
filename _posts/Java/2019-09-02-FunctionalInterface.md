---
layout: post
title: Java Functional Interface
category: Java
tags:
- Java
---

자바 함수적 인터페이스
=================

### 1. 함수적 인터페이스?
- 어렴풋이 알던 내용 정리
- java.util.function
- 람다식 사용

### 2. 종류

#### 1. Consumer
- 매개값은 있고, 리턴값은 없다.
- 매개값 -> Consumer
- interface : accept(), andThen()
```java
Consumer<String> c1 = t -> System.out.println(t + "8");
c1.accept("consumer");

c1.andThen(after -> {
    System.out.println("andThen");	
}).accept("consumer");

BiConsumer<String, String> c2 = (t, u) -> System.out.println(t + u);
c2.accept("consumer", "8");

DoubleConsumer dc = d -> System.out.println("consumer" + d);
dc.accept(8.0);

IntConsumer ic = i -> System.out.println("consumer" + i);
ic.accept(8);

LongConsumer lc = l -> System.out.println("consumer" + l);
lc.accept(8);

ObjDoubleConsumer<String> odc = (t, d) -> System.out.println(t + d);
odc.accept("consumer", 8.0);

ObjIntConsumer<String> oic = (t, i) -> System.out.println(t + i);
oic.accept("consumer", 8);

ObjLongConsumer<String> olc = (t, l) -> System.out.println(t + l);
olc.accept("consumer", 8);
```

#### 2. Supplier
- 매개값은 없고, 리턴값은 있다.
- Supplier -> 리턴값
- interface : get()
```java
Supplier<String> supplier = () -> {
    return "1";
};
System.out.println("supplier" + supplier.get());

IntSupplier is = () -> {
    int a = (int) (Math.random() * 6) + 1;
    return a;
};
System.out.println("supplier" + is.getAsInt());
```

#### 3. Function
- 매개값도 있고, 리턴값도 있다. (매개값을 리턴값으로 매핑(형변환))
- 매개값 -> Function -> 리턴값
- interface : apply(), compose(), andThen()
```java
Function<Integer, String> function = t -> {
    return "function" + t;
};

// compose (before function)
System.out.println(function.compose(t -> {
    return Integer.parseInt((String) t); 
}).apply("8"));

// andThen (after function)
System.out.println(function.andThen(f -> {
    return f + "andThen";
}).apply(8));

// apply
System.out.println(function.apply(8));
```



#### 4. Operator
- 매개값도 있고, 리턴값도 있다. (매개값을 연산하고 결과 리턴)
- 매개값 -> Function -> 리턴값
```java
// BiFunction 하위 인터페이스
// apply(), compose(), andThen()
BinaryOperator<String> bo = (l, r) -> {
    return l + r;
};
System.out.println(bo.apply("java", "8"));

// Function 하위 인터페이스
// apply(), compose(), andThen()
UnaryOperator<String> uo = t -> {
    return t + "8";
};
System.out.println(uo.apply("java"));

// 2개의 int 연산
IntBinaryOperator ibo = (l, r) -> {
    return l + r;
};
System.out.println("1 + 2 = " + ibo.applyAsInt(1, 2));
```

#### 5. Predicate
- 매개값은 있고, 리턴타입은 boolean (매개값 조사후 boolean 리턴)
- 매개값 -> Function -> boolean
- interface : test(), negate(), and(), or(), isEqual()
```java
public static void main(String[] args) {
    Predicate<Example> examplePredicate = t -> {
        return t.getField().equals("java");
    };
    System.out.println(examplePredicate.test(new Example("java")));
    System.out.println(examplePredicate.test(new Example("")));
}

@Getter
@Setter
@ToString
@AllArgsConstructor
public class Example {
    private String field;
}
```

### 3. Reference
- https://altongmon.tistory.com/245