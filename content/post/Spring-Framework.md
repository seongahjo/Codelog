+++
categories = ["JAVA"]
date = "2018-09-25T13:56:47+00:00"
description = ""
draft = true
tags = ["Java", "Spring Framework", "Framework"]
title = "Spring Framework"

+++
### Spring Framework

JAVA 애플리케이션 개발에 사용하는 경량 프레임워크.

Spring Framework의 특징은 6개로 정리할 수 있다.

#### 경량

***

POJO (Plain Old Java Object)를 사용하여 크기와 기능성을 가볍게 만들었다.

Plain Old Java Object란

> 클래스 상속, 인터페이스 구현 및 어노테이션을 강제하지 않는 자바 객체

#### 관점 지향 프로그래밍 (AOP)

***

애플리케이션의 비지니스 로직을 구현하는 로깅, 인증 등의 다양한 기능들을 분리하여 원할 때 재사용이 가능하도록 만들었다.

#### 트랜잭션 관리

***

Java Transaction API (JTA), JDBC, Hibernate, Java Persistence API (JPA), Java Data Objects (JDO)같은 여러 가지 트랜잭션 API간에 일관성있는 프로그래밍 모델

선언적인 트랜잭션 관리 지원. (@Transactional)

프로그래밍적인 트랜잭션 관리에 대해 JTA 같은 복잡한 트랜잭션 API보다 더 간단한 API.

스프링의 데이터 접근 추상화와의 뛰어난 통합.

#### 컨테이너

***

애플리케이션의 객체들의 생명주기 (lifecycle)와 설정을 컨테이너가 관리한다.

#### 의존성 주입 (DI)

***

Spring Framework가 느슨히 연결된 애플리케이션 개발을 가능하게 하는 특징. 느슨히 연결된 애플리케이션은 유닛 테스트에 용이하다. 개발자들이 원할 때 모듈을 교체할 수 있도록 한다.

#### 타 프레임워크와의 연동

***

Ibatis, Hibernate, Toplink등 다양한 프레임워크와의 연동이 잘 되있다.