+++
categories = ["Java"]
date = "2018-10-20T08:57:28+00:00"
description = ""
draft = true
tags = ["Spring Framework"]
title = "Spring batch"

+++
### Spring Batch

#### Job

Job은 여러 개의 Step을 포함하고 있는 객체. Step의 컨테이너.

#### JobInstance

`JobRepository`를 통해 조회 또는 생성되며 Job의 논리적 실행 단위 객체. job의 `name`과 `id`로 필드가 선언되있다.

#### JobExecution

`JobRepository`를 통해 조회 또는 생성되며 Batch가 Job을 한번 실행할 때마다 생성된다. Job 실행시 필요한 정보를 담고 있다. 현재 실행되고 있는 Batch의 상태를 `BatchStatus`에 담고 있다.

#### JobParameter

Job을 실행하는데 필요한 파라미터 정보를 key-value 형식으로 담고 있다.

#### JobRepository

* JobInstance
* JobExecution
* JobExecutionParamter
* StepExecution

들을 저장하고 조회한다.

#### Step

하나의 Job은 여러 개의 Step으로 이루어져 있다. Step에서 Batch Job을 처리하는 작업의 일부 또는 전체를 수행한다. Step은 `ItemReader`, `ItemProcessor`, `ItemWriter`을 포함하거나 `Tasklet`을 포함한다.

#### StepExecution

JobExecution은 Job의 상태와 Job을 실행시키기 위한 속성을 포함하고 있다. StepExeuction은 Step의 상태와 Step을 실행시키기 위한 속성을 포함하고 있다.

#### StepBuilder

Step을 샐성하기 위한 클래스다.

`JobBuilderFactory`를 통해 `Job`을 만들고 `StepBuilderFactory`를 통해 `Step`을 만든다.

#### StepExecutionListener

`void beforeStep(StepExecution stepExecution)`와 `ExitStatus afterStep(StepExecution stepExecution)`을 메소드로 가지고 있음.

#### Tasklet

Chunk 기반에서 `ItemReader`, `ItemProcessor`, `ItemWriter`를 하나로 합친 단위.

모든 작업을 순차적으로 진행한다.

복구가 불가능하다.

#### @ConditionOnProperty

조건에 의해 실행

Batch 작업시 `Configuration`에 `job`, `step` bean이 필요하다.

`step` bean은 구체적인 작업 내용

`job` bean은 작업 순서 등. (Flow Control)

ItemWriter 모아서 List를 만드는거지 List를 입력받지 않음.

입력받으려면 ItemWritert를 재정의 해야함.