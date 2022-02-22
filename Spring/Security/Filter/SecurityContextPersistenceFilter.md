### 2-4-1. SecurityContextPersistenceFilter

보통 두 번째로 실행되는 Filter임.

> 첫 번째 Filter는 Async 요청에 대해서도 SecurityContext를 처리할 수 있도록 도와주는 `WebAsyncManagerIntegrationFilter`임.

<br>

이 Filter는 `SecurityContext를 찾아와서 SecurityContextHolder에 넣어주는 역할`을 함.

만약 SecurityContext를 찾았는데 없다면, 그냥 새로 하나 만들어줌.