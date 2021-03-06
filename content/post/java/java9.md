+++
categories = ["Java"]
date = "2018-10-27T14:31:33+00:00"
description = ""
draft = true
tags = ["Java9"]
title = "Java9"

+++
### Java9

#### JShell

Java용 REPL(Read-Eval-Print-Loop), 간단한 Code Snippet 실행 가능.

#### Collection Factory Method

Immutable한 Collection을 생성한다.

기존 Guava에서 제공하던 불변 List, Set, Map, Map.Entry 생성 가능

`List.of(values...)` `Map.of(key,value,key,value,...)`

기존방식 `Collections.unmodifiableList(list)`

#### Project Jigsaw

module system

`exports`를 통해 외부에 노출되는 패키지를 설정.

`requires`를 통해 패키지에 필요한 모듈을 지정.

jlink tool을 통해 runtime에 JDK에서 필요한 라이브러리들을 호출한다.

이건 자세히 알아볼 필요가 있따...

```java
module de.codecentric.zipvalidator{
	exports de.codecentric.zipvalidator.api;
}
```

[Manual](http://openjdk.java.net/projects/jigsaw/quick-start)

[실제 예](https://www.linkedin.com/pulse/java-9-pain-gain-jigsaw-massimiliano-dal-mas)

#### Process API 개선

#### try-with-resources 개선

#### Diamond Operator 개선

내부 익명 클래스에서 diamond operator 사용 가능.

#### Interface Private Method

인터페이스 내에서 Private 메소드 사용 가능.

#### Reactive Stream API 추가

#### Stream API 개선

`dropWhile`

Iterate를 보조하는 연산. 정렬된 스트림에 한해서 사용해야함.

정렬되지 않으면 순서가 랜덤으로 되서 매번 반환하는 스트림이 다름.

해당 조건을 만족하면 해당 요소를 삭제하고 만족하지 않으면 종료.

```java
Stream.of(2, 4, 6, 8, 9, 10, 12)
	.dropWhile(n -> n % 2 == 0)
    .forEach(System.out::println)
```

`takeWhile`

Iterate를 보조하는 연산. 정렬된 스트림에 한해서 사용해야함.

정렬되지 않으면 순서가 랜덤으로 되서 매번 반환하는 스트림이 다름.

앞에서부터 순서대로 해당 조건을 만족하면 냅둔다.

만족하지 않으면 종료.

```java
Stream.of(2, 4, 6, 8 , 9, 10, 12)
	.takeWhile(n -> n % 2 ==0)
	.forEach(System.out::println);
// 2 4 6 8
```

`ofNullable`

null이 의심되는 객체를 Stream으로 Wrapping하는데 쓰임.

```java
collection.stream()
	.flatMap(s -> Stream.ofNullable(map.get(s))
    .collect(Collectors.toList())
```

`Optional.of(1).stream()` optional to stream

#### HTTP2 Client

`HttpClient` 클래스

`HttpRequest`

`HttpResponse`

#### Multi-release JARs

Java version에 따라 다른 버전의 라이브러리를 제공함. (하위 호환성이 더 좋아짐)

[참조](https://medium.com/@goinhacker/java-9%EC%9D%98-%EB%B3%80%ED%99%94%EC%99%80-%ED%8A%B9%EC%A7%95-%EB%8C%80%EC%B6%A9-%EC%A0%95%EB%A6%AC-fca77cee88f2)

[참조2](https://www.pluralsight.com/blog/software-development/java-9-new-features)