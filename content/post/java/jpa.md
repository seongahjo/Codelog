+++
categories = ["Java"]
date = "2018-10-20T14:23:21+00:00"
description = ""
draft = true
tags = ["JPA"]
title = "JPA"

+++
### JPA

#### Fetch

* FetchType.EAGER
* FetchType.LAZY

#### Cascade

* CascadeType.PERSIST 엔티티를 `persist()`하면 관련된 엔티티도 `persist()`해준다.
* CascadeType.MERGE 트랜잭션이 종료되고 detach 된 상태에서 연관 엔티티를 추가하거나 변경된 이후에 부모 엔티티가 merge()를 수행하면 변경사항이 적용된다.
* CascadeType.REMOVE
* CascadeType.DETACH
* CascadeType.ALL