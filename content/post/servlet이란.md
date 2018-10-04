+++
categories = ["웹"]
date = "2018-10-04T14:10:03+00:00"
description = ""
draft = true
tags = ["Servlet"]
title = "Servlet이란"

+++
## Servlet

  서블릿 컨테이너는 개발자가 웹 서버와 통신하기 위해 소켓을 생성하고 특정 포트에 리스닝하고 스트림을 생성하는 등의 복잡한 일을 대신 해준다. 컨테이너는 Servlet의 생성과 소멸까지 일련의 과정(Life Cycle)을 관맇나다. 서블릿 컨테이너는 요청이 들어올때 마다 새로운 자바 스레드를 만든다.

사용자가 URL을 클릭하면 HTTP Reqeust를 Servlet Container에 보낸다.

Servlet Container는 HttpServletRequest, HttpServletResponse 두 객체를 생성한다(?)

사용자가 요청한 URL을 분석하여 어느 서블릿에 대한 요청인지 찾는다

컨테이너는 서블릿 service() 메소드를 호출하며 Method의 종류에 따라 doGet()또는 doPost()가 호출된다.

doGet() 이나 doPost() 메소드는 동적인 페이지를 생성한 후 HttpServletResponse 객체에 응답을 보낸다.

응답이 완료되면 두 객체를 소멸시킨다.

서블릿의 생명주기

init() -> 서블릿이 켜질 떄 한번 실행

service - 요청을 받을 때 실행 => doGet(), doPost()

destory() 서버가 꺼질 떄 한번 실행 

ApplicationContext(와 BeanFactory)가 Spring Container의 역할을 한다. Bean들의 생명주기를 관리한다.