+++
categories = []
date = "2018-10-03T09:46:25+00:00"
description = ""
draft = true
tags = []
title = "Spring MVC 처리구조"

+++
## Spring MVC 처리구조

클라이언트의 모든 요청이 Dispatcher Servlet에 전달된다. dispatcher servlet은 Front Controller로 Spring servlet를 이루는 구조중 하나다.

Dispatvher servlet은 요청을 HandlerMapping으로 보내 어떤 Controller에서 처리가 가능한지 확인한다.

web.xml은 Servlet 3.0부터 `WebApplicationInitializer`에 의해 대체되었다.

DispatvherServlet은 `AnnotationConfigWebApplicationContext`을 참조하여 설정을 한다.

Controller내 `@RequestMapping` Annotation을 통해 어떤 메소드에서 처리 가능한지 확인하고 해당 메소드에서 처리한다.

ContextLoaderListener 

Viewresolver

MultipartResolver

대표적인 Servlet Container는 톰캣이다. WAS파일을 읽어 Servlet 객체를 생성해 관리한다. Servlet Container는 요청이 들어올 때마다 Servlet을 생성한다.