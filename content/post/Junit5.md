+++
categories = ["JAVA"]
date = "2018-09-26T09:24:54+00:00"
description = ""
draft = true
tags = ["java", "test", "junit5", "junit"]
title = "Junit5"

+++
### JUnit

#### 사용방법

`assert boolean식`

#### Import 방법

`import static org.junit.Assert.*;`

####  두 값이 같은지 비교

`assertEquals( expected, actual)`

####  두 객체가 동일한 객체인지 비교

`assertSame( expected, actual )`

`assertNotSame ( expected,  actual)`

####  참 / 거짓 판별

`assertTrue( expected )`

`assertFalse( expected )`

####  Null여부 판단

`assertNull( expected )`

`aseertNotNull( expected )`

#### 테스트 실패로 판단

`fail()`

#### 배열 일치

`assertArrayEquals( expected, actual)`

#### 하나로 묶기

`assertAll( Executable....)`

#### Exception으로 판단

`assertThrows( Exception.class, 함수)`

#### 어노테이션

`@BeforeClass`

테스트 클래스 내에서 수행 전 한 번만 실행, static method여야 함

`@AfterClass`

테스트 클래스 내에서 수행 후 한 번만 실행, static method여야 함 

`@Before`

테스트 케이스 수행 전 반복 실행

`@After`

테스트 케이스 수행 후 반복 실행

`@Test`

테스트 메소드 지정

`@RunWith`

Runner 클래스 설정하는 어노테이션. Junit에 내장된 Runner 대신 그 클래스를 실행.

@ExtendWith을 쓰는 것을 추천

####  Junit 4 VS Junit5

* package가 jupiter pacakge로 바뀌었다.
* Annotation 이름변경
  * BeforeClass -> BeforeAll
  * Before -> BeforeEach
  * After -> AfterEach
  * AfterClass-> AfterAll
  * Runwith -> ExtendWith