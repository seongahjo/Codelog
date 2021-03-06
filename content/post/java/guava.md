+++
categories = ["Java"]
date = "2018-10-27T13:32:48+00:00"
description = ""
draft = true
tags = ["Guava"]
title = "Guava"

+++
### Guava

Guava는 구글이 만든 자바 오픈소스 라이브러리

제공하는 기능은 크게 다섯가지가 있다.

#### 컬렉션 초기화와 유틸리티

생성자가 아닌 메서드를 통해 컬렉션 초기화 가능.

Java9에서 제공

#### 함수형 스타일의 프로그래밍

`map`, `filter` 등의 메소드를 제공.

Java8에서 제공

#### Multimaps과 Bimaps

바이맵은 키(Key)처럼 값(Value)의 유일함을 강제한다.

#### 쉬운 해시코드(Hashcode)와 비교자(Comparator)

`Objects` 클래스를 통해 `hashCode`를 쉽게 생성하는 방법을 제공.

`ComparisonChain` 클래스를 통해 Comparator 제공.

#### 방어적 코딩

`checkArgument`

#### Date 처리

`LocalDate` 클래스를 통해 처리 가능

`Range` 클래스도 있음.

#### I/O

#### Math

#### 대체

`StringBuilder`사용했 던 것을 `Objects.toStringHelper()`로 대체 가능

각 클래스 비교시 `Objects.equals()`를 통해 구현할 수 있다.

삼항연산자를 `Objects.firstNonNull()`로 대체 가능.

if문으로 null 비교했던 거를 static 메소드 `checkNotNull()`로 대체 가능.

CharMatcher는 regrex를 대체할 수 있단다.

`Joiner`를 통해 String 연결할 때 조건문 넣을 수 있음.

`Splitter`를 통해 String 분리할 수 있음.

ImmutableMap, Set을 만들 수 있다.

`Files.readLines()`를 통해 파일을 읽을 수 있다.