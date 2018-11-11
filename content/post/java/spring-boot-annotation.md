+++
categories = ["Java"]
date = "2018-11-09T11:02:58+00:00"
description = ""
draft = true
tags = ["Spring Boot"]
title = "Spring Boot Annotation"

+++
## Spring Boot Annotation

### `@EnableWebMvc`

Spring Boot가 아닌 그냥 Spring에서 사용하는 Annotation, Spring Boot는 필요없다.

`RequestMappingHandlerMapping`, `RequestHandlerAdapter`, `ExceptionHandler`, `ExceptionResolver`, `MessageConverter` 등 빈을 자동으로 등록해준다.

`@Component`

해당 어노테이션이 적용된 클래스를 빈으로 등록한다. `@ComponentScan` 어노테이션을 통해 컴포넌트가 스캔이 된다.

`@Scope` 어노테이션과 연계하여 프록시 설정이 가능하다. 

`@Service`

`@Required`

`@Bean`

`@Scope`

`@Resource`

`@Autowired`

1. 이 어노테이션을 변수 위에 선언할 경우 스프링에서 의존성 주입을 해준다.
2. 이 어노테이션을 세터(Setter) 위에 선언할 경우 클래스가 생성시 세터에 정의된 대로 의존성이 주입된다.

### `@SpringBootApplication`

스프링 부트 애플리케이션이라는 것을 명시하는 어노테이션. 

내부에 `@SpringBootConfiguration`, `@EnableAutoConfiguration`, `@ComponentScan`을 포함하고 있다.

### `@SpringBootConfiguration`

`@Configuration`이 내부에 포함도있다. 애플리케이션에는 무조건 하나의 `@SpringBootConfiguration`을 포함하고 있어야한다.

### `@EnableAutoConfiguration`

`@Import`, `@AutoConfigurationPackage`

스프링 애플리케이션 컨텍스트의 자동 설정을 가능하게 해준다.