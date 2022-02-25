### 4-2-3. Schema

Batch를 실행하고 관리하기 위한 metadata가 저장됨.

Spring batch가 실행될 때 각각의 class를 생성하고 사용하게 되는데 그 기록들을 데이터베이스화 해서 남기는 것.

![](https://docs.spring.io/spring-batch/docs/current/reference/html/images/meta-data-erd.png)

- Spring Batch Framework가 실행 시 metadata table들을 사용하므로 초기 설정이 필요함.

- 보통 수정하지 않고 조회만 함.

- Job 이력, parameter 등 실행 결과를 조회할 수 있음.

- Batch 결과에 대해 log, 별도의 실행 이력을 남기는 경우가 대부분이라 조회할 일이 많지 않음.

