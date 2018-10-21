+++
categories = ["Java"]
date = "2018-10-21T14:26:53+00:00"
description = ""
draft = true
tags = ["enum"]
title = "Enum"

+++
### Enum

Java에서 Enum은 class다.

#### 사용예시 1

```java
public enum enumName{
	enumValue1, enumValue2, enumValue3	
}
```

#### 사용 예시2

```java
public enum enumName{
	enumValue1("일"), enumValue2("이"), enumValue3("삼");	
	
    final private String name;	
	private enumName(String name){	
		this.name = name;	
	}
    
	public String getName(){	
		return name;	
	}
 }
```

#### 함수

`enumName.values()` enum 내의 모든 값들 반환

`enumName.enumValue1.ordinal()` enumValue1의 int값 반환

`enumName.valueOf("enumValue1")` enumValue1 반환

#### 참조

[Java Enum 활용기 (우아한 형제들 기술블로그)](http://woowabros.github.io/tools/2017/07/10/java-enum-uses.html)