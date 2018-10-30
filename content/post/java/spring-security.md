+++
categories = ["Java"]
date = "2018-10-30T09:59:00+00:00"
description = ""
draft = true
tags = ["Spring", "Spring Security", "Spring Framework"]
title = "Spring Security"

+++
### Spring Security

보안의 3요소

* 접근 주체 (Principal) 보호된 대상에 접근하는 사용자
* 인증 (Authenticate) 현재 사용자가 누구인지 확인하는 과정
* 인가 (Authorize) 현재 사용자가 특정 URL, 기능 들에 접근할 수 있는 권한이 있는지 검사하는 작업.

Principal은 `Authentication`에서 가져올 수 있다.

`Authentication`은 `SecurityContext`에서 가져올 수 있다.

`SecurityContext`는 `SecurityContextHolder`를 통해 가져올 수 있다.

#### Authentication

현재 접근 주체 (Principal)의 정보, 인증 주체(Authority)의 정보를 담는 객체

#### SecurityContextHolder

SecurityContext를 가지고 있는 객체이다. `SecurityContextHolder.MODE``_INHERITALBLETHREADLOCAL_`_,_ `_SecurityContextHolder._``MODE_THREADLOCAL`이라는 두가지 방법을 제공한다.

#### Authenticate (인증)

인증은 Spring Security의 AuthenticationManager를 통해 처리하게 된다. 실질적인 인증 처리는 Manager에 등록된 `AuthenticationProvider`를 통해 처리된다. AuthenticationManager의 구현체는 따로 만들지 않고 `ProviderManager`를 사용한다. `AuthenticationProvider`만 교체하는 식으로 인증을 구현한다.

`AuthenticationProvider`는 `AuthenticationProviderBuilder`를 통해서 등록한다?

##### AuthenticationManager

인증을 처리하는 객체. 인증 성공시 인증 정보를 담은 Authentication 객체를 리턴한다. 실질적인 인증은 `AuthenticationProvider`에 의해 처리된다. 

인증 성공시 Spring Security는 Authentication 객체를 SecurityContext에 저장하고 인증 상태 유지를 위해 세션에 보관한다. 인증 실패시 `AuthenticationException`을 발생시킨다

[참조](https://tramyu.github.io/java/spring/spring-security/)