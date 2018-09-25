+++
categories = ["JAVA"]
date = "2018-09-25T14:17:18+00:00"
description = ""
draft = true
tags = ["Spring Framework", "java"]
title = "Bean의 생명주기"

+++
### Bean의 생명주기

#### 생성

##### IntializingBean 인터페이스

Spring에서 기본적으로 제공해주는 `InitializingBean` 인터페이스를 구현하면 초기화 작업을 할 수 있다. `afterPropertiesSet()` 함수를 재정의하면 된다.

##### @PostConstruct

`@PostConstruct` 어노테이션을 통해 초기화 작업을 할 수 있다.

##### @Bean(initMethod)

`@Bean(initMethod)` @Bean 어노테이션을 통해 빈을 등록할 때는 어노테이션에 있는 initMethod 속성을 설정하면 된다.

#### 제거

##### DisposaleBean 인터페이스

`DisposableBean`인터페이스를 구현하면 된다. `destory()`함수를 재정의하면 된다.

##### @PreDestory

`@PreDestory` 어노테이션을 통해 삭제시 작업을 설정할 수 있다.

##### @Bean(destoryMethod)

`@Bean`어노테이션을 통해 빈을 등록할 때 어노테이션에 있는 destoryMethod 속성을 설정하면 된다.