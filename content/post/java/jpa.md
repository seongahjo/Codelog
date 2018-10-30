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

* FetchType.EAGER JOIN 연산을 통해 연관 객체를 한번에 다 얻어온다.
* FetchType.LAZY 일단 proxy 객체를 리턴하고 실제로 필요할 때 데이터베이스에서 조회한다.

#### Cascade

* CascadeType.PERSIST 엔티티를 `persist()`하면 관련된 엔티티도 `persist()`해준다.
* CascadeType.MERGE 트랜잭션이 종료되고 detach 된 상태에서 연관 엔티티를 추가하거나 변경된 이후에 부모 엔티티가 `merge()`를 수행하면 변경사항이 적용된다.
* CascadeType.REMOVE 엔티티를 삭제하면 연관된 엔티티도 같이 삭제됨
* CascadeType.DETACH 부모 엔티티가 `detach()`를 수행하면 연관된 엔티티도 `detach()`실행 되어 변경사항이 적용 안된다.
* CascadeType.ALL 위의 모든 CascadeType이 적용된다.

#### persistence context

메모리에 존재하는 공간. 실제 물리적 공간에 저장하려면 `flush()`를 해야함.