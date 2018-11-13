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

* default method
* static method

### Java 9

* private method

### Functional Interface

`@FunctionalInterface` 어노테이션을 인터페이스 위에 선언하면 된다.

한 개의 추상화된 메소드만을 가지고 있으면 된다.

즉 default method, static method, private method 다 상관없음.

### VS Abstract Class

`abstract` 키워드를 통해 선언한다.

추상 메소드 또한 `abstract` 키워드를 포함한다.

추상 메소드는 있어도 되고 없어도 된다.

추상 메소드가 존재하면 추상 클래스를 상속받는 클래스는 구현을 무조건 해야한다. 다만 추상 클래스가 추상 클래스를 상속받을경우 구현할 필요가 없다.

Abstract Class와 Interface의 차이는 상속(Inheritance) vs 구현(Implementation) 의 차이라고 볼 수 있다.

상속은 공통적인 부분, 필드, 메소드 다 포함을 상위 클래스가 가지고 있고 상위 클래스의 확장이 필요할 때 사용한다.

구현은 같은 메소드를 공유하고 구현만 달리한다. 느슨한 결합이 가능하다. (loosely coupled) (추상화, 다형성)