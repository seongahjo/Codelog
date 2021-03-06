+++
categories = ["Go"]
date = "2018-09-28T09:40:29+00:00"
description = ""
draft = true
tags = ["입사", "Kakao", "Go"]
title = "카카오 2차 시험 준비하기"

+++
### 면접준비

***

실력 테스트 및 자극을 받고자 봤던 **2019 KAKAO BLIND RECRUITMENT**에 온라인 테스트에 합격했다. 합격을 하리라고 생각조차 한 적이 없어서 당황스러웠다.  시간이 얼마 남지 않아 부랴부랴 급히 준비하고 있다. 작년 시험을 살펴본 결과 `멀티쓰레드`와 `REST API` 요청 및 예외처리를 활용하는 문제가 나와서 비슷하게 나올 것이라 생각하고 관련 내용들을 준비하고 있다.

#### 언어 선택

***

이것 저것 다양한 분야를 개발해봤지만 `멀티쓰레드`를 제대로 해본 적이 없다. 그나마 **인터넷 프로토콜**시간에 실습으로 해본 것이 전부다. 한 번쯤은 해봐야지 라고 생각을 했었으나 이걸 입사 시험에서 만나게 될줄이야. 개인적으로 언어적으로  `멀티쓰레드`를 하기 적합한`Java`와 `Go`중에서 고민을 했다.

##### Java

***

###### 장점

JAVA는 간단히 `Synchronized` 키워드를 통해 CS에 대한 경합을 방지할 수 있고 Thread-Safe한 자료구조들을 제공한다는 점에서 사용을 고려했다. 알고리즘을 JAVA로 풀어서 현시점에서 Java 숙련도가 가장 높다는 장점도 있다.

###### 단점

JDK를 마음대로 쓸 수 없는 현재 여건 상 연습을 할 수 없다.

##### Go

***

###### 장점

Go에는 경량 쓰레드인 `Goroutine`과 `Goroutine`사이의 통신을 가능하게 하는 `Channel`이 있다. 사용도 간단하다는 점이 매력적이다. 또한 Go로 진행한 프로젝트가 없다는 점 또한 Go를 선택지에 넣은 이유다. 매번 프로젝트를 다른 언어로 진행하면서 얻은 점이 많았다. 이번에도 많은 걸 얻어갈 수 있을 것 같다. 마지막으로 Go로 코딩할 수 있는 환경을 만들었다는 점이다. 아무리 이론이 빠삭하다 해도 코드로 만들지 못하면 쓸모가 없다. 결론은 코드로 말해야한다.

###### 단점

Go가 익숙하지 않다.

##### 결론

***

장점의 길이만 비교하더라도 알 수 있다. 결론은 Go로 시험을 보기로 했다. 이번 기회가 흔히 오는 기회가 아니라 익숙한 Java를 쓸까 생각했지만 Go를 써보고 싶다는 내 욕망을 이기지 못했다.  계속 공부하면서 작년과 비슷하게 나온다면 Go를 쓰는게 더 좋은 결과가 있을 것 같다고 느꼈다. 올바른 선택이었기를 바란다. 하하핳

```go
package main
import (
	"fmt"
	"sync"
)
func main() {
	var wg sync.WaitGroup
	input := make(chan int)
	for i := 0; i < 11; i++ {
		wg.Add(1)
		go func(input chan<- int, r int) {
			input <- r
			wg.Done()
		}(input, i)
	}
	for i := 0; i < 11; i++ {
		fmt.Println(<-input)
	}
	close(input)
	wg.Wait()
}
```