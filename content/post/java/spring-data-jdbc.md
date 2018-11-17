+++
categories = ["Java"]
date = "2018-11-17T08:10:09+00:00"
description = ""
draft = true
tags = ["Spring Data JDBC"]
title = "Spring Data JDBC"

+++
## Spring Data JDBC

caching, lazy loading, dirty checking

dirty checking은 JPA마다 다르며 Hibernate에서는 inspection이라는 전략을 사용한다.  객체가 대이터베이스에서 불러와질 때 스냅샷을 찍고 메모리에 저장해놓는다. 세션이 Flush될 때 Hibernate는 스냅샷과 현재 상태를 비교한다. 만약 다르다면 dirty라고 마킹한 후 적절한 SQL이 실행된다.

Spring Data JPA처럼 Data Entity에 따라 테이블을 생성해주지 않는다. 직접 생성해야한다. 또한 dirty checking을 지원하지 않아 OneToMany 관계의 경우 테이블의 필드를 수정하면 해당 테이블이 가지고 있는 Child들을 다 삭제하고 다시 추가한다.

[참조](https://spring.io/blog/2018/09/17/introducing-spring-data-jdbc)

[dirty checking](https://vladmihalcea.com/the-anatomy-of-hibernate-dirty-checking/)