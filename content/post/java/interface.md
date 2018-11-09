+++
categories = ["Java"]
date = "2018-11-09T02:46:12+00:00"
description = ""
draft = true
tags = ["interface"]
title = "interface"

+++
## Interface

> 인터페이스는 자바 프로그래밍 언어에서 클래스들이 구현해야 하는 동작을 지정하는데 사용되는 추상형이다. 메소드 시그니처와 상수 선언 (static과 final이 둘 다 선언되는 변수 선언) 만을 포함할 수 있다.

### Java8

* +default method
* +static method

### Java 9

* +private method

### Functional Interface

`@FunctionalInterface`를 인터페이스 위에 추가하면 된다.

한 개의 추상화된 메소드만을 가지고 있으면 된다.

default method, static method, private method 다 상관없음.