+++
categories = ["Java"]
date = "2018-11-17T07:22:55+00:00"
description = ""
draft = true
tags = ["Junit", "Junit4", "Junit5"]
title = "Junit5"

+++
## Junit5

Junit4는 Java5 이상을 지원하고 Junit 라이브러리 안에 모든 기능이 내장되있다.

하지만 Junit5는 3가지 모듈로 나누어져 있다.

* Junit Platform JVM 환경에서 테스트 프레임워크를 수행. (JUnitPlatform.class)
* Junit Jupiter 새로운 assert문, 어노테이션, lambda 표현식 등 확장 기능이 포함되어있다.
* Junit Vintage Junit3, Junit4를 Junit5에서 실행할 수 있게 지원하는 모듈.

Junit5는 Java 8 이상부터 지원한다.

Annotation이 살짝 변경되었다.

ex) `@BeforeAll` -> `@BeforeClass`, `@BeforeEach` -> `@Before`

Assert도 살짝 변경되었다.

`assertThat`이 사라지고 `assertAll`, `assertThrows`가 추가되었다. 또한 메세지 파라미터가 마지막으로 옮겨졌다.

assume?