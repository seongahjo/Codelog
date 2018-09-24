
, Golang, 비동기, 멀티쓰레드, go, golang]
##고루틴
Go 언어에서 제공하는 경량 스레드
* 2KB의 스택 공간만 필요하다. 다만 필요에 따라 Heap을 확보한다. (쓰레드는 1MB로 시작한다)

**채널을 통한 데이터 전송을 추천**

### 타임아웃
```go
select{
	case res := <-c1:
		fmt.Println(res)
	case <-time.After(time.Second*1):
	fmt.Println("timeout 1")
}
```

### 비동기 채널
`select`문에 default문을 함께 사용하면 비동기 송수신을 구현할 수 있다.


### 채널 닫기
채널 닫기는 더이상 채널에 보낼 데이터가 없음을 나타낸다.
채널의 리시버들에게 완료 상태를 전달할 때 유용하다.

`j, more := <- jobs`
에서 more은 해당 채널이 close됐는지를 리턴해준다.

`done` channel을 통해 메인 고루틴에서 워커 고루틴이 끝날 때까지 대기를 한다.

### 채널 Range
채널을 닫으면 range를 통해 값을 수신할 수 있다.


### Timer와 Ticker
고루틴을 응용한 타이머와 티커
`time` package 안에 존재한다.
* `time.NewTicker(시간)`
* `time.NewTimer(시간)`

ticker.C를 통해 
* 대기
* 작업의 반복

을 구현할 수 있다.

둘다 Stop 메소드를 통해 중지시킬 수 있다.

### Worker Pool
1. `jobs` 채널을 두고 처리해야하는 데이터들을 다 넣어둔다.
2. 처리가 끝난 데이터를 넣을 수 있도록 `result` 채널을 만든다
3. 작업 내용을 정리한 `Worker`함수를 만든다.  *worker 함수는 `jobs`, `result` 채널을 매개변수로 받는다*

```go
package main

import "fmt"
import "time"

func worker(id int, jobs <-chan int, results chan<- int) {
	for j := range jobs {
		fmt.Println("worker", id, "started  job", j)
		time.Sleep(time.Second)
		fmt.Println("worker", id, "finished job", j)
		results <- j * 2
	}
}

func main() {

	jobs := make(chan int, 100)
	results := make(chan int, 100)

	for w := 1; w <= 3; w++ {
		go worker(w, jobs, results)
	}
	
	for j := 1; j <= 5; j++ {
		jobs <- j
	}
	close(jobs)
	
	for a := 1; a <= 5; a++ {
		fmt.Println(<-results)
	}
}
```


### 속도 제한
> 속도 제한은 리소스 이용을 제어하고 서비스의 품질을 유지하기 위한 중요한 매커니즘입니다. Go는 고루틴, 채널 그리고 티커로 속도 제한을 지원합니다.

**속도제한을 통해 배치 처리(Batch Processing)를 구현할 수 있다.**

## 공유 자원 접근 방법

###원자성 카운터
여러 개의 고루틴에서 접근을 할 수 있는 `원자성 카운터 (atomic counter)`를 알아보자
`sync/atomic` 패키지에서 제공한다.
아래 두가지 함수를 자주 쓴다
* `AddUint64(&uint64, 값)`
* `LoadUint64(&uint64)`

###Mutex
`sync` 패키지의 `Mutex`를 사용한다.

#### 초기화
` var mutex = &sync.Mutex{}`
#### 잠금 및 해제
` mutex.Lock()`
`mutex.Unlock()`


###채널을 통한 잠금
[링크](https://mingrammer.com/gobyexample/stateful-goroutines/)
