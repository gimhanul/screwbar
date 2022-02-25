## 4-2. Spring Batch Architecture

![](https://docs.spring.io/spring-batch/docs/current/reference/html/images/spring-batch-reference-model.png)

**domain 언어**


- JobLauncer : Job을 실행시키는 component임.
- Job : Batch의 작업임.
- JobRepository : Job을 실행하며 Job, Step을 저장함.
- Step : Batch 작업의 단계를 나타냄.
    - ItemReader : 데이터를 읽음.
    - ItemProcessor : 데이터를 처리함.
    - ItemWriter : 데이터를 씀.

<br>

**Architecture**

- Application Layer
    - 사용자 코드와 구성.
    - 비즈니스, 서비스 로직.
    - Core, Infrastructure를 이용해 batch의 기능을 만듦.

- Core Layer
    - batch 작업을 시작하고 제어하는 데 필수적인 클래스임.
    - Job, Step, JobLauncer.

- Infrastructure Layer
    - 외부와 상호작용.
    - ItemReader, ItemWriter, RetryTemplate