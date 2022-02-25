### 4-2-2. Step

Step은 `작업 처리의 단위`임.

Chunk 기반 스텝, Tasklet 스텝 두 가지로 나뉨.

<br>

**Chunk-oriented Step**

![](https://docs.spring.io/spring-batch/docs/current/reference/html/images/chunk-oriented-processing-with-item-processor.png)

- chunk 기반으로 `하나의 transaction`에서 데이터를 처리함.

- 한 번에 commitInterval 만큼 데이터를 읽고 처리하며 chunkSize 만큼 다 읽었을 때, transaction 경계 내에서 한 번에 write함.

    |용어|설명|
    |--|--|
    |chunkSize|한 transaction에서 write할 item의 개수|
    |commitInterval|reader가 한 번에 read할 item의 개수|

<br>

다음과 같이 구현함.

```java
@Bean
public Job sampleJob(JobRepository jobRepository, Step sampleStep) {
    retun this.jobBuilderFactory.get("sampleJob")
        .repository(jobRepository)
        .start(sampleStep)
        .build();
}

@Bean
public Step sampleStep(PlatformTransactionManager tranactionManager) {
    return this.stepBuilderFactory.get("sampleStep")
        .transactionManager(transactionManager)
        .<String, String>chunk(10)
        .reader(itemReader())
        .writer(itemWriter())
        .build();
}
```
- ItemReader, ItemProcesser, ItemWriter 구현체를 설정함.

- ItemProcessor는 생략할 수 있음.
    > 간단한 내용이라면 생략하고 Writer에 작성함.

<br>

<br>

**Tasklet Step**

- 데이터를 읽고, 처리하고, 쓰는 과정이 하나의 transaction 안에서 일어남.

- 단순한 처리를 할 때 사용함.

<br>

다음과 같이 구현함.

```java
@Bean
public Step step1() {
    return this.stepBuilderFactory.get("step1")
            .tasklet(myTasklet())
            .build();
}
```
-  Tasklet 구현체를 설정하며, 내부에 단순한 읽기, 처리, 쓰기 로직을 모두 몰아 넣음.

- RepeatStatus(반복 상태)를 설정함.
    > Tasklet 내부에서 일어나는 일을 종료할건지 반복할건지 결정하는 Status임.

    > 보통 데이터가 잘 처리됐다면, RepeatStatus.FINISHED를 설정함.