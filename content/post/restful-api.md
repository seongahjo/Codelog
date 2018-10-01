+++
categories = ["면접"]
date = "2018-09-28T09:10:27+00:00"
description = ""
draft = true
tags = ["Web", "RESTful"]
title = "RESTful API"

+++
### RESTful API

> 월드 와이드 웹(World Wide Web)과 같은 분산 하이퍼미디어 시스템을 위한 **소프트웨어 아키텍처**의 한 형식으로 **자원**을 정의하고 자원에 대한 주소를 지정하는 방법 전반에 대한 패턴

REST는 REpresentational State Transfer의 약자이다. 여기에 \~ful 이라는 형용사형 어미를 붙여 \~한 API라는 표현으로 사용된다. REST의 기본 원칙을 성실히 지킨 서비스 디자인을 'RESTful'하다고 표현한다.

#### REST는 디자인 패턴인가 아키텍처인가?

아키텍처다. REST는 Resource Oriented Architecture다. API 설계의 중심에 자원(Resource) 이 있고 HTTP Method를 통해 자원을 처리하도록 설계하는 것이다.

#### REST의 6가지 원칙

* Uniform Interface
* Stateless
* Caching
* Client-Server
* Hierarchical system
* Code on demand

#### RESTful하게 API를 디자인 한다는 것을 무엇을 의미하는가

1. **리소스**와 **행위**를 명시적이고 직관적으로 분리한다.
   * 리소스는 URI로 표현된다. 리소스가 가리키는 것은 **명사**로 표현되야 한다.
   * 행위는 HTTP Method로 표현하고 GET, POST, PUT, DELETE를 분명한 목적으로 사용한다.
2. Message는 Header와 Body를 명확하게 분리해서 사용한다
   * Entity에 대한 내용은 Body에 담는다.
   * API 정보, 응답받고자 하는 MIME타입 등은 header에 담는다.
   * header와 body는 http header와 http body로 나눌 수 있고 http body에 들어가는 json 구조로 분리할 수도 있다.
3. API 버전을 관리한다.
   * 버전에 따라 API의 signature가 변경될 수도 있다.
   * 특정 API를 변경할 때는 반드시 하위 호환성을 보장해야한다.
4. 서버와 클라이언트가 같은 방식을 사용해서 요청하도록 한다.
   * 브라우저는 form-data 형식의 submit으로 보내고 서버에서는 json 형태로 보내는 식의 분리보다는 클라이언트와 서버가 같은 방식으로 보내야 한다.
   * URI가 플랫폼 중립적이어야 한다. 플랫폼에 종속되면 안된다.

##### 장점

1. Open API를 제공하기 쉽다
2. 멀티플랫폼 지원 및 연동이 용이하다.
3. 원하는 타입으로 데이터를 주고 받을 수 있다.
4. 기존 웹 인프라(HTTP)를 그대로 사용할 수 있다.;

##### 단점

1. 사용할 수 있는 메소드가 4가지이다.
2. 분산환경에 부적합하다
3. HTTP 통신 모델에 대해서만 지원한다.