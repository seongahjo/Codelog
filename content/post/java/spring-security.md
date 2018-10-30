+++
categories = ["Java"]
date = "2018-10-30T09:59:00+00:00"
description = ""
draft = true
tags = ["Spring", "Spring Security", "Spring Framework"]
title = "Spring Security"

+++
### Spring Security

보안의 3요소

* 접근 주체 (Principal) 보호된 대상에 접근하는 사용자
* 인증 (Authenticate) 현재 사용자가 누구인지 확인하는 과정
* 인가 (Authorize) 현재 사용자가 특정 URL, 기능 들에 접근할 수 있는 권한이 있는지 검사하는 작업.

Principal은 `Authentication`에서 가져올 수 있다.

`Authentication`은 `SecurityContext`에서 가져올 수 있다.

`SecurityContext`는 `SecurityContextHolder`를 통해 가져올 수 있다.