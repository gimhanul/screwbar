### 4-2-1. Job

Job은 `전체 batch process를 캡슐화`한 domain임.

Step의 순서를 정의하며, JobParameters를 받음.


<br>

![](https://docs.spring.io/spring-batch/docs/current/reference/html/images/job-stereotypes-parameters.png)

위 예시에서

1. Job을 수행했을 때
2. JobInstance기 실제로 Job을 실행할 때마다 바뀌는 JobParameters를 가지고 만들어짐.
    > JobInstance는 실제로 Job이 실행되는 객체임.
3. Job을 여러 개로 나눈 JobExcution이 실행됨.
    > JobExcution은 실질적으로 Job이 실행되는 것임.