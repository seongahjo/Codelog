+++
categories = ["Java"]
date = "2018-10-20T09:51:19+00:00"
description = ""
draft = true
tags = ["Annotation"]
title = "Annotation"

+++
### Annotation

어노테이션은 **소스 코드에 메타데이터**를 표시하는 것. 리플렉션을 이용하면 어노테이션 지정으로 원하는 클래스를 주입할 수 있음. ex) `@Autowired`

* `@Retention` 어노테이션의 적용 시점을 정할 수 있다.
* `@Documented` 문서에서도 어노테이션의 정보가 표현된다.
* `@Target` 어노테이션이 적용될 위치를 결정한다.
* `@Inherited` 자식 클래스가 어노테이션을 상속 받을 수 있다.
* `@Repeatble` 반복적으로 어노테이션을 선언할 수 있다.
* `@Scope` 어노테이션의 범위를 정할 수 있다.

#### 선언법

```java
public @interface AnnotationName{
public enum enumName {aa,bb}

// String
String value();
// 배열
int[] values();

enumName enum() default enum.aa;
}
```

#### 중요한 어노테이션

##### @Retention

* `RetentionPolicy.RUNTIME` 컴파일 이후에도 JVM에 의해서 참조가 가능하다.
* `RetentionPolicy.CLASS` 컴파일러가 클래스를 참조할 때까지 유효하다.
* `RetentionPolicy.SOURCE` 어노테이션 정보는 컴파일 이후 없어진다.

##### @Target

* `ElementType.PACKAGE` 패키지 선언시
* `ElementType.TYPE` 타입 선언시
* `ElementType.CONSTRUCTOR` 생성자 선언시
* `ElementType.FIELD` 멤버 변수 선언시
* `ElementType.METHOD` 메소드 선언시
* `ElementType.ANNOTATION_TYPE` 어노테이션 타입 선언시
* `ElementType.LOCAL_VARIABLE` 지역 변수 선언시
* `ElmentType.PARAMETER` 매개 변수 선언시
* `ElementType.TYPE_PARAMETER` 매개 변수 타입 선언시
* `ElementType.TYPE_USE` 타입 사용시

##### @Scope

###### value

* request 요청시 마다 새로 생성
* singleton (deafult)
* prototype `getBean()`하는 시점마다 새로운 빈 객체를 생성해준다.
* session 세션 내 유일한 빈을 생성

###### proxyMode

* ScopedProxyMode.NO 프록시를 생성하지 않는다
* ScopedProxyMode.INTERFACES 인터페이스에 대해 프록시를 생성
* ScopedProxyMode.TARGET_CLASS CGLIB을 사용하여 클래스에 대한 프록시 생성
* ScopedProxyMode.DEFAULT

###### CGLIB

CGLIB은 코드 생성 라이브러리 (Code Generator Library)

런타임에 동적으로 자바 클래스의 프록시를 생성해주는 기능을 제공한다.

스프링은 프록시 기반의 AOP를 구현할 때 CGLIB을 사용하고 있다.

`Reflection`을 통해 어노테이션이 적용된 곳을 찾고 주입할 수 있다. 

`java.lang.reflect`