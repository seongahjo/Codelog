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

현재 실행하고 있는 스레드의 `SecurityContext`를 가지고 있는 객체이다. `SecurityContextHolder.MODE_INHERITALBLETHREADLOCAL`_,_ `SecurityContextHolder.MODE_THREADLOCAL`이라는 두가지 방법을 제공한다.

`ThreadLocal`은 특정 한 스레드에서만 읽고 저장할 수 있다.

`InheritableThreadLocal`은 자식 스레드가 부모 스레드의 `ThreadLocal` 값을 읽고 저장해야하는 상황에서 사용한다. `InheritableThreadLocal`에 저장된 값은 특정 스레드와 자식 스레드까지 읽고 저장할 수 있다.

`InheritableThreadLoca`l은 `ThreadLocal`의 서브 클래스다.

#### Authenticate (인증)

인증은 Spring Security의 AuthenticationManager를 통해 처리하게 된다. 실질적인 인증 처리는 Manager에 등록된 `AuthenticationProvider`를 통해 처리된다. AuthenticationManager의 구현체는 따로 만들지 않고 `ProviderManager`를 사용한다. `AuthenticationProvider`만 교체하는 식으로 인증을 구현한다.

`AuthenticationProvider`는 `AuthenticationProviderBuilder`를 통해서 등록한다?

##### AuthenticationManager

인증을 처리하는 객체. 인증 성공시 인증 정보를 담은 Authentication 객체를 리턴한다. 실질적인 인증은 `AuthenticationProvider`에 의해 처리된다.

인증 성공시 Spring Security는 Authentication 객체를 SecurityContext에 저장하고 인증 상태 유지를 위해 세션에 보관한다. 인증 실패시 `AuthenticationException`을 발생시킨다

Provider 등록은 `WebSecurityConfigureAdapter`를 상속해 만든 `SecurityConfig`에서 할 수 있다. WebSecurityConfigureAdapter는 AuthenticationManger를 가지고 있어 Custom Provider를 등록할 수 있다.

[참조](https://tramyu.github.io/java/spring/spring-security/)

[필터 참조](http://javacan.tistory.com/entry/58)

***

### CORS

#### SOP

Same-Origin Policy 동일 출처 정책, 한 출처에서 로드된 문서나 스크립트가 다른 출처 자원과 상호작용 못하도록 하는 제약. 두 Origin간 프로토콜, 포트, 호스트가 같아야 통신이 가능하다.

호스트, 프로토콜이 달라도 통신이 가능하게 해준다.

웹 서버 도메인간 엑세스 제어 기능을 제공하여 보안 도메인간 데이터 전송을 가능하게 해준다.

동작과정

1. Pre-Flight Request 실제 요청하려는 경로와 같은 URL에 OPTIONS 메소드로 요청.

#### 적용방법

##### 로컬 CORS 적용

Spring 4.2이후부터 `@CrossOrigin`을 사용하여 쉽게 해결할 수 있다.

##### 전역 CORS 적용

`WebMvcConfigureAdapter`의 멤버 메소드인 `addCorsMappings`를 Override해서 해결이 가능하다.

`public void addCorsMappings(CorsRgistry registry)`를 Override해서 Global CORS 설정이 가능하다.