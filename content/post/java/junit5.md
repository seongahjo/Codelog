+++
categories = ["Java"]
date = "2018-11-17T07:22:55+00:00"
description = ""
draft = true
tags = ["Junit", "Junit4", "Junit5"]
title = "Junit5"

+++
## JUnit5

### 구조

#### JUnit4

JUnit4는 Java5 이상을 지원하고 한 라이브러리 안에 모든 기능이 내장되있다.

#### JUnit5

하지만 Junit5는 Java8 이상부터 지원하며 3가지 모듈로 나누어져 있다.

* JUnit Platform JVM 환경에서 테스트 프레임워크를 수행. (JUnitPlatform.class)
* JUnit Jupiter 새로운 assert문, 어노테이션, lambda 표현식 등 확장 기능이 포함되어있다.
* JUnit Vintage JUnit3, JUnit4를 JUnit5에서 실행할 수 있게 지원하는 모듈.

### Annotation

#### JUnit4

`@BeforeAll`

`@Before`

`@Ignore`

#### JUnit5

`@BeforeClass`

`@BeforeEach`

`@Disabled`

### Assert

#### JUnit4

`assertThat`

추가됨

추가됨

메세지가 첫 번째 파라미터임. 

#### JUnit5

사라짐

`assertAll`

`assertThrows`

메세지가 마지막 파라미터임.

### 동기/비동기

#### JUnit4

JUnit4는 한 번에 한 개의 러너밖에 실행할 수 없음.

#### JUnit5

JUnit5는 동시에 다수의 러너를 실행시킬 수 있다.

JUnit4까지는 `@Test(expected= Excetion.class)`이런식으로 했지만 JUnit5에서는 `assertThrows(Exception.class, ()->{})`이런식으로 처리할 수 있다.

JUnit4까지 그룹 테스트를 진행할 때 사용하던 `@Category`가 `@Tag`로 대체됐다.

`@Tag`는 클래스와 메소드 위에 붙일 수 있다.

JUnit4까지 `@Runwith(SpringRunner.class)`였던 것이 `@ExtendWith(SpringExtension.class)`으로 대체됐다.

`@Rule`로 공통적인 테스트 환경을 구성했던 것이 `AfterEachCallback`, `BeforeEachCallback` 인터페이스를 구현하는 것으로 대체됐다.

```gradle
junitPlatform{
	filters{
    	tags{
        	exclude project.hasProperty('runIntegrationTests') ? '' : 'integration-test'
            }
		}
  }
```