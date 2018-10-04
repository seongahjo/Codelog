+++
categories = ["Deisgn Pattern"]
date = "2018-10-04T14:37:27+00:00"
description = ""
draft = true
tags = ["Adapter Pattern", "Adapter"]
title = "Adapter Pattern"

+++
## Adapter Patter

한 클래스의 인터페이스를 클라이언트에서 사용하고자 하는 다른 인터페이스로 변환할 수 있는 디자인 패턴.

어댑터를 이용하면 인터페이스 호환성 문제 때문에 같이 사용할 수 없는 클래스들을 연결해서 쓸 수 있다.

Adapter는 Target Interface를 Implementation하며 Target Interface를 사용하고자 하는 Adaptee 인스턴스를 가지고 있다.

객체 어댑터와 클래스 어댑터