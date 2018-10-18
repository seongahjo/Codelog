+++
categories = ["지원"]
date = "2018-10-18T16:24:00+00:00"
description = ""
draft = true
tags = ["Naver", "Hackday"]
title = "Naver Hackday 지원"

+++
### Naver Hackday 지원기

#### 15. Contents Feed Backend 시스템

##### 요구사항

* `Redis` 또는 `MongoDB` 기반의 데이터 처리 / 연동 구현
* 컨텐츠 라이프 싸이클 관리를 위한 `배치` 구현
* REST API의 구현, 성능 최적화
* 컨텐츠 캐싱 전략 수립 및 구현

##### 공부해야할 것

* Redis
* MongoDB
* Spring Batch

#### 20. 결제 패턴 분석 웹 서비스 개발

##### 요구사항

* 데이터셋을 받을 수 있는 인터페이스 개발 (File Stream 등)
* 주어진 데이터셋을 기반으로 유의미한 데이터 도출
* 데이터 분석 알고리즘 설계 및 개발
* 결제 데이터 패턴 분석 결과 제공 웹서비스 개발
* 설계 시스템의 Class & Sequence Diagram

##### 공부해야할 것

* Apache Spark?
* Diagram

##### 24. 지도 검색 실시간 트렌드

##### 요구사항

* `Spark`를 사용해서 지도 데이터를 정형화된 포멧으로 변환 및 저장
* 지도 검색 `랭킹` 모델링
* 지도 검색 서비스 개발
* 로그 기반, 급상승 인기 검색어 및 급상승 인기 장소 추출 및 display (`kibana`이용)

##### 공부해야할 것

* Spring boot2
* Spark2
* Elsatic Search 6.x
* Kibana

Macbook PRO? 제공해주다는건가?

#### 12. 뉴스 연재 기사 클러스터링 시스템

##### 요구사항

* 검색 API, 형태소 API을 `호출`하고 결과물을 파싱하여 데이터로 활용하는 능력
* 연재를 발굴하고 저장할 수 있는 `배치` 개발
* 발굴된 연재 내용을 확인하고 서비스 반영을 제어할 수 있는 `어드민` 개발
* 기계학습 적용
* 참신한 아이디어 적용

[API 명세 링크](https://m.news.naver.com/hotissue/main.nhn?sid1=110&cid=1073439)

##### 공부해야할 것

* Spring Batch

#### 7. 트렌드 모아보기

##### 요구사항

* 1개 이상 트렌드 조회 오픈 API 사용
* 2개 이상 컨텐츠 조회 오픈 API 사용
* 결과 화면은 텍스트, 이미지 , 동영상의 조합으로 이루어져야함
* 지난 트렌드 모아보기 기능
* Test code