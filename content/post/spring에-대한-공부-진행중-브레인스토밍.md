+++
categories = []
date = "2018-10-04T14:08:44+00:00"
description = ""
draft = true
tags = []
title = "Spring에 대한 공부 진행중 브레인스토밍"

+++
Front Controller Pattern

* 웹 애플리케이션과 관련된 패턴
* 모든 리소스 요청을 처리해주는 하나의 컨트롤러를 두는 패턴
  * DispatcherServlet

webinitilaizer에 Config 파일들을 등록한다. Servlet 이름, Servlet에 Mapping되는 패턴들을 등록한다. 필터도 등록한다.

`DisptacherServlet`은 설정과 메타 데이터들을 `WebApplicationContext`에서 참조한다.

data repository나 bussiness service들을 처리하는 빈들을 이곳에 등록한다. `Controller`, `ViewResolver`, `HandlerMapping`이 이곳에 등록된다.

rootwebapplicationcontext != webapplicationcontext

rootwebapplicationcontext는 공통적인 설정

webapplicationcontext는 각각 Servlet에 대한 개별 설정

ContextLoaderListener가 성생한 Context가 root Context가 된다.

webapplication context, locale resolver, theme resolver, theme source

`context`란 어떤 객체를 핸들링 하기 위한 접근 수단

`Flash Map`은 한 요청에서 다른 요청으로 파라미터를 넘길 때 사용하는 일반적인 패턴이다.

web.xml은 Servlet 3.0부터 `WebApplicationInitializer`에 의해 대체되었다.

`DispatcherServlet`은 context Class로 `AnnotationConfigWebApplicationContext`을 참조하여 설정을 한다.

`dispatch`함수는 리퀘스트 처리할 적절한 핸들러를 찾는다. 핸들러는 일반적으로 특정한 객체이며 특정 인터페이스에 제한되지 않는다. 따라서 스프링은 핸들러와 어떻게 통신할 것인지를 나타내는 어댑터를 필요로 한다. 요청에 맞는 핸들러를 찾기위해 다양한 `HandlerMapping` 인터페이스의 구현으로 처리한다.

`SimpleUrlHandlerMapping`은 요청을 URL과 컨트롤러와 연결시킨다.

`RequestMappingHandlerMapping` 요청을 `@Controller`클래스의 `@RequestMapping`에 매핑된 메소드와 연결시킨다.

`render()`함수 `LocaleResovler 개체`

ModelAndView

`HttpMessageConverter`

Controller내 `@RequestMapping` Annotation을 통해 어떤 메소드에서 처리 가능한지 확인하고 해당 메소드에서 처리한다.

ContextLoaderListener

View Resolver

MultipartResolver

대표적인 Servlet Container는 톰캣이다. WAS파일을 읽어 Servlet 객체를 생성해 관리한다. Servlet Container는 요청이 들어올 때마다 Servlet을 생성한다.

configuration에서 FilterRegistrationBean를 리턴값으로 bean으로 만들면 필터를 추가할 수 있음 혹은 `@Component` , `@WebFiler`을 통해서

Request -> Filter -> Dispatcher Servlet -> Handler Mapping -> (D.S) -> Handler Adapter -> Controller -> 요청 처리 결과를 Model에 담고 View의 이름을 HandlerAdapter에 전달-> DispatcherServlet은 View이름을 가지고 ViewResolver에 요청해서  View를 찾음 -> Response에 View를 담아 리턴 -> Filter를 통해 Response로 감