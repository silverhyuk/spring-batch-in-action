# spring-batch-in-action

Spring Batch In Action이 2011년 이후 개정판이 나오지도 않고, 한글 번역판도 없고, 국내 Spring Batch 글 대부분이 튜토리얼이거나 공식문서 번역본이라 답답해서 시작  
커머스나 기타 서비스 시스템이 커질수록 배치 작업이 늘어나는데, 주먹구구식으로 Spring Batch 사용하는 경우가 많음  
Spring MVC는 자료가 정말 많지만 Batch는 너무 없어서 정리도 할겸 시작.  

> 잘되면 책낼수 있지 않을까?  

## 목차

예정

* Simple Batch Job
    * 잡실행 결과 리뷰
    * Job, JobInstance, JobExecution 등등 BATCH_JOB 스키마
        * BatchExecution 테이블 내용물 리뷰
    * BatchStatus 소개
* Batch Job Flow
    * Step
    * Flow
    * split & mutli Thread
    * decide
        * JobExecutionDecider를 통한 Step 분기처리

* Batch 실행
    * 여러개 Job 중 원하는 Job 만 수행하려면?
        * ```spring.batch.job.names``` 소개
        * ```${job.name:NONE}``` 없을 경우 아무것도 실행하지 않고, 있으면 해당 Job만 실행 
* JobParameter
    * ```@StepScope```, ```@Value```
    * Build => batch.jar 를 실행 => console에 출력되는 파라미터 확인
    * Job Parameter 중복으로 오류나는것도 확인
    * 테스트 코드로 build 없이 수행하는것 확인
* Reader
    * custom reader 생성시 ```read()``` 메소드 오버라이딩 주의 사항
        * ```this.data.hasNext()``` 가 false일 경우 무조건 null 반환하도록
        * null이 반환안되면 무한 읽기 시작됨
    * DB & JPA
        * JpaItemReader
        * JpaPagingItemReader
        * JpaCursorItemReader
        * QuerydslPagingItemReader & QuerydslCursorItemReader
    * File
        * FlatFileItemReader
    * Read Multiple DataSources
* Writer
    * DB & JPA
    * Write Multiple DataSources
* Processor
* 테스트 코드
* Batch 스케줄링은 어떻게? (젠킨스)

