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

Spring Data JPA처럼 Data Entity에 따라 테이블을 생성해주지 않는다. 직접 생성해야한다. 또한 dirty checking을 지원하지 않아 OneToMany 관계의 경우 테이블의 필드를 수정하면 해당 테이블이 가지고 있는 Child들을 다 삭제하고 다시 추가한다.

[참조](https://spring.io/blog/2018/09/17/introducing-spring-data-jdbc)

[dirty checking](https://vladmihalcea.com/the-anatomy-of-hibernate-dirty-checking/)