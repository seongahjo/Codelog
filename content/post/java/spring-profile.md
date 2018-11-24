+++
categories = ["Java", "Spring"]
date = "2018-08-29T15:00:00.000+00:00"
draft = true
tags = ["Spring", "Profile"]
title = "Spring Profile"

+++
## Spring Profile

`@Profile`과 `@ActiveProfiles` 차이

`@Profile`을 통해 각 환경에 맞게 Spring의 Bean들을 설정할 수 있다.

### @Profile

#### 사용법

`@Profile("이름")`으로 설정한다.

Profile Annotation은 클래스와 메소드에 적용이 가능하다. 

`@Profile("!이름")`으로 Not 설정도 가능하다.

Bean이름을 통일하려면 중첩 클래스를 사용하는 것을 추천한다.

### @ActiveProfiles

테스트를 할 때 사용하는 어노테이션. 테스트를 할 때 사용할 Profile을 설정할 수 있다.

#### 사용법

`@ActiveProfiles("프로파일 이름")`

`resolver`와 `inheritProfiles`를 속성으로 가진다.

##### resolver

##### inheritProfiles

상속을 설정하는 옵션

`false`로 설정할 경우 슈퍼클래스의 profile을 적용하지 않는다.

`true`일 경우 슈퍼클래스의 profile을 적용한다.

### IfProfileValue

name, value를 속성으로 가진다.

name의 속성이 value일경우 해당 테스트를 실행한다.