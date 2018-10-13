+++
categories = ["Java", "Spring Framework"]
date = "2018-10-03T09:46:25+00:00"
description = ""
draft = true
tags = ["Spring Framework", "MVC", "Spring Framework MVC"]
title = "Spring MVC 처리구조"

+++
##  Spring MVC 처리구조

![](/uploads/2152594E590431631F.jpg)

클라이언트의 모든 요청이 `Filter`를 거쳐 `DispatcherServlet`에 전달된다. `DispatcherServlet`은 Front Controller로 Spring servlet를 이루는 구조중 하나다. `DispatcherServlet`은 요청들을 받아서 Controller로 보내주는 역할을 한다. 

어떤 Controller로 보내는지 알기 위해 요청을  `HandlerMapping` 로 보낸다. `HandlerMapping`에서 Controller를 결정하고 `DispatcherSerlvet`에서 `HandlerAdapter`를 통해 해당 Controller로 보낸다.

Controller에서 비지니스 로직을 처리하고 비지니스 로직을 View 이름과 함께  `ModelAndView`에 담아 `DispatcherServlet`에 돌려준다.

`DispatcherServlet`은 View 이름을 `ViewResolver`에 보내 원하는 View를 받아오고 데이터를 View에 적용한 후 요청의 결과값으로 반환한다. 반환된 View는 `Filter`를 지나 클라이언트에게 보내진다. 

###### 용어

* Filter
* DispatcherServlet
* Front Controller
* Spring Servlet
* HandlerMapping
* HandlerAdapter
* ViewResolver