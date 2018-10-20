+++
categories = ["Database"]
date = "2018-10-20T10:25:25+00:00"
description = ""
draft = true
tags = ["InnoDB", "MyISAM"]
title = "InnoDB vs MyISAM"

+++
### InnoDB vs MyISAM

자주 쓰이는 MySQL의 스토리지 엔진에는 InnoDB와 MyISAM이 있다.

둘의 차이점은

* 트랜잭션의 유무
* Locking의 범위 차이
* 데이터의 순서 유무
* 회복(복구) 기능 유무

가 있다.

MyISAM은 Select연산이 InnoDB에 비해 빠르다.