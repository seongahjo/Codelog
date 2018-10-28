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

Java용 REPL(Read-Eval-Print-Loop), 간단한 Code Snippet 실행 가능

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

#### Process API 개선

#### try-with-resources 개선

#### Diamond Operator 개선

내부 익명 클래스에서 diamond operator 사용 가능.

#### Interface Private Method

인터페이스 내에서 Private 메소드 사용 가능.

#### Reactive Stream API 추가

#### Stream API 개선

`dropWhile` d

`takeWhile` d

`ofNullable` d

`iterate` 개선

`Optional.of(1).stream()` optional to stream

#### HTTP2 Client

`HttpClient` 클래스

`HttpRequest` d

`HttpResponse` d

#### Multi-Resolution Image API

#### Multi-release JARs

Java version에 따라 다른 버전의 라이브러리를 제공함. (하위 호환성이 더 좋아짐)

[참조](https://medium.com/@goinhacker/java-9%EC%9D%98-%EB%B3%80%ED%99%94%EC%99%80-%ED%8A%B9%EC%A7%95-%EB%8C%80%EC%B6%A9-%EC%A0%95%EB%A6%AC-fca77cee88f2)

[참조2](https://www.pluralsight.com/blog/software-development/java-9-new-features)

interface에서

java8

default method

static method도 가능

java 9

private method도 가능 