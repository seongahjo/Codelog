+++
categories = []
date = "2018-10-03T09:46:25+00:00"
description = ""
draft = true
tags = []
title = "Spring MVC 처리구조"

+++
## Spring MVC 처리구조

클라이언트의 모든 요청이 `DispatcherServlet`에 전달된다. `DispatcherServlet`은 Front Controller로 Spring servlet를 이루는 구조중 하나다.

`DispatcherServlet`은 요청을 `HandlerMapping`으로 보내 어떤 Controller에서 처리가 가능한지 확인한다.

webapplication context, locale resolver, theme resolver, theme source

`Flash Map`은 한 요청에서 다른 요청으로 파라미터를 넘길 때 사용하는 일반적인 패턴이다.

web.xml은 Servlet 3.0부터 `WebApplicationInitializer`에 의해 대체되었다.

`DispatcherServlet`은 context Class로 `AnnotationConfigWebApplicationContext`을 참조하여 설정을 한다.

`dispatch`함수는 리퀘스트 처리할 적절한 핸들러를 찾는다. 핸들러는 일반적으로 특정한 객체이며 특정 인터페이스에 제한되지 않는다. 따라서 스프링은 핸들러와 어떻게 통신할 것인지를 나타내는 어댑터를 필요로 한다. 요청에 맞는 핸들러를 찾기위해 다양한 `HandlerMapping` 인터페이스의 구현으로 처리한다.

`SimpleUrlHandlerMapping`은 요청을 URL과 특정 빈과 연결시킨다.

Controller내 `@RequestMapping` Annotation을 통해 어떤 메소드에서 처리 가능한지 확인하고 해당 메소드에서 처리한다.

ContextLoaderListener 

View Resolver

MultipartResolver

대표적인 Servlet Container는 톰캣이다. WAS파일을 읽어 Servlet 객체를 생성해 관리한다. Servlet Container는 요청이 들어올 때마다 Servlet을 생성한다.