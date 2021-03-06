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

둘의 차이점은 아래와 같다.

* 트랜잭션의 유무
* Locking의 범위 차이
* 데이터의 순서 유무
* 회복(복구) 기능 유무

MyISAM은 Select연산이 InnoDB에 비해 빠르다. 풀 텍스트 인덱스를 지원한다. 풀 텍스트 인덱스는 하나 이상의 컬럼의 집합에서 검색이 가능한 방법.

InnoDB는 데이터 크기가 바뀌어도 이전에 경험했던 최대 크기로 유지된다. 따라서 한 번 커진 데이터 파일은 안에 데이터를 삭제해도 용량이 동일하다.