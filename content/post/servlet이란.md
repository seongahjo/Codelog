+++
categories = ["웹"]
date = "2018-10-04T14:10:03+00:00"
description = ""
draft = true
tags = ["Servlet"]
title = "Servlet이란"

+++
## Servlet

서블릿 컨테이너(=아파치 톰캣)는 개발자가 웹 서버와 통신하기 위해 소켓을 생성하고 특정 포트에 리스닝하고 스트림을 생성하는 등의 복잡한 일을 대신 해준다. 컨테이너는 Servlet의 생성과 소멸까지 일련의 과정(Life Cycle)을 관리한다. 서블릿 컨테이너는 요청이 들어올때 마다 새로운 자바 스레드를 만든다.

자바 서블릿은 자바를 사용하여 웹페이지를 동적으로 생성하는 서버측 프로그램 또는 그 사양을 뜻한다. (Wikipedia)

서블릿 컨테이너는 요청마다 프로세스보다 가벼운 스레드로 응답한다.

서블릿이 요청받으면 `service()` 메소드가 호출된다. 이 메소드는 `request.getMethod()` 메소드를 기반으로 `doGet()` 혹은 `doPost()` 같은 메소드 중 하나를 호출한다. 해당되는 메소드가 서블릿에 없다면 응답에 HTTP 405 에러가 리턴된다.

서블릿 컨테이너는 JSESSION란 이름으로 key, 생성한 session ID를 value로 HTTP 응답의 Set-Cookie header에 cookie로 설정한다.

ServletContext는 **웹 애플리케이션**이 실행할 때 생성되며 메모리에 저장한다. 모든 session에서 모든 request간 공유가 된다.

서블릿 컨테이너가 종료되면 모든 웹 애플리케이션이 언로드되고 모든 서블릿과 필터의 `destory()`를 실행한다.

사용자가 URL을 클릭하면 HTTP Reqeust를 Servlet Container에 보낸다.

사용자가 요청한 URL을 분석하여 어느 서블릿에 대한 요청인지 찾는다

요청이 오면 `HttpServletRequest`, `HttpServletResponse`가 생성이 된다. 그리고 컨테이너 내부적으로 재사용을 한다.

서블릿과 필터는 모든 request에서 공유된다.

서블릿 객체는 다수의 쓰레드에 의해 동시에 사용될 수 있다.

서블릿의 생명주기

init() -> 서블릿이 켜질 떄 한번 실행

service - 요청을 받을 때 실행 => doGet(), doPost()

destory() 서버가 꺼질 떄 한번 실행

context에 따라 Container 개수가 달라짐? 아마두?

application context Container와

Servlet Container 두가지 있음.

ApplicationContext(와 BeanFactory)가 Spring Container의 역할을 한다. Bean들의 생명주기를 관리한다.

#### 서블렛 컨테이너와 웹 서버가 어떻게 사용자의 요청을 처리하는가

1. 웹서버가 HTTP 요청을 받는다.
2. 웹서버가 요청을 서블릿 컨테이너에게 건내준다.
3. 서블릿 컨테이너에 요청에 해당하는 서블릿이 없을경우 동적으로 서블릿이 할당된다.
4. 컨테이너가 서블릿을 초기화를 하기 위해 init()을 호출한다. (처음 호출했을 때만)
5. 컨테이너가 서블릿의 service()를 호출한다. service()에서 request에서 데이터를 받아서 가공 후 response에 넣어 반환한다. 서블릿은 컨테이너의 메모리에 남아서 다른 요청을 처리한다.

`HttpServletRequest`는 body의 내용을 한 번만 읽을 수 있다. 

ServletRequest, ServletResponse

[참조](https://okky.kr/article/372195)