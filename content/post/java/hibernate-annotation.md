+++
categories = ["Java"]
date = "2018-11-10T05:10:02+00:00"
description = ""
draft = true
tags = ["Annotation", "Hibernate"]
title = "Hibernate Annotation"

+++
## Hibernate Annotation

### `@Entity`

Entity Bean을 선언해주는 어노테이션

### `@Table`

데이터베이스 테이블 명 선언하는 어노테이션

### `@Id`

id 컬럼을 지정하는 어노테이션

### `@GeneratedValue`

데이터베이스에게 id컬럼에 auto-increment를 명시적으로 지시하는 어노테이션

strategy

### `@Column`

컬럼을 지정하는 어노테이션

### `@Version`

버전을 지정하는 어노테이션

### `@OrderBy`

데이터를 정렬하는 어노테이션

### `@Transient`

### `@Lob`

큰 데이터를 저장할 때 쓰는 어노테이션 (CLOB,BLOB)

### `@ManyToOne`

1:N의 관계를 나타냄. 이 어노테이션이 가리키는 필드(객체)를 가지고 있으면 해당 필드와 매칭되는 컬럼의 개수는 N개.

### `@OneToMany`

N:1의 관계를 나타냄. 이 어노테이션이 가리키는 필드(리스트)를 가지고 있으면 해당 필드와 매칭되는 컬럼의 개수는 1개.

두개를 꼭 한번에 같이 쓸 필요 없음.