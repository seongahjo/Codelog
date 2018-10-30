+++
categories = ["JAVA"]
date = "2018-09-26T09:17:02+00:00"
description = ""
tags = ["java", "Spring", "Annotation"]
title = "Spring Annotation"

+++
### **Spring Framework Annotation**

#### **@Autowired**

***

의존성을 주입하여 자동으로 객체를 생성해주며 메소드 위에 사용할 경우 기본생성자를 만들어준다 타입에 따라 매핑되기 때문에 동일 인터페이스를 상속받을 경우 구분의 모호함이 발생할 수 있음

#### **@Qualifer**

***

Type에 따라 매칭되는 @Autowired의 불편함을 줄여주기 위해 @Autowired 어노테이션 밑에 사용하여 특정 Bean을 가리켜준다.

```java
@Autowired 
@Qualifier("test")
Inteface i;
```

#### **@Resource**

***

Autowired와 Qualifier를 합친 형태

`@Resource(name = "빈이름 ")`형식으로 사용.

#### **@Component**

***

#### **@Aspect**

***

공통적인 부분을 가지는 클래스 위에 써서 공통 Bean을 만든다.

#### **@Pointcut**

***

aspect bean 객체 내에 있는 공통의 메소드를 언제 실행할 것인가에 대한 조건.

`@Pointcut("execution(public * sp.aop.service.*.()``_)"_`

* execution
* within
* this
* target
* args
* @target
* @args
* @within
* @annotation

#### **@around**

***

pointcut에 들어가는 advice를 감싸는 부분. `@Before`, `@After` advice를 포함

##### 실행순서

* `@Before`
* `@Around` 
* 대상 메소드 
* `@Around` 
* `@After`
* `@AfterReturning`

#### **@RequestMapping**

***

특정 URI에 매핑되는 클래스나 메소드임을 명시해준다.

Spring 4.3 부터 method를 따로 명시안해줘도 되는 어노테이션들이 추가됐다.

* `@GetMapping`
* `@PostMapping`
* `@PutMappin`
* `@PatchMapping`
* `@DeleteMapping`

#### **@Controller**

***

스프링 MVC 컨트롤러 객체임을 명시한다.

#### **@RequestParam**

***

요청에서 특정한 파라미터의 값을 찾아낼 때 사용

#### **@Repository**

***

`@Component`의 하위 계층이며 DAO 객체임을 명시한다

#### **@Service**

***

`@Component`의 하위 계층이며 Service 객체임을 명시한다.

#### **@ModelAttribute**

***

자동으로 해당 객체를 뷰까지 전달한다.

#### **@PathVariable**

***

현재의 URI에서 원하는 정보를 추출

#### **@SessionAttribute**

***

세션상에서 모델의 정보를 유지하고 싶은 경우에 사용