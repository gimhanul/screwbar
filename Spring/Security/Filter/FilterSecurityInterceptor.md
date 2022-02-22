### 2-4-7. FilterSecurityInterceptor

Interceptor로 끝나지만 Filter 맞음. 아무튼 맞음.

FilterSecurityInterceptor는 넘어온 authentication의 내용을 기반으로 `최종 인가 판단`을 내림.

> 👉🏻 Filter 중 뒤쪽에 위치함.

- Authentication을 가져오고, 문제가 있다면 AuthenticationException을 발생함.
- Authentication에 문제가 없으면 인가를 판단함.
- 인가가 거절된다면 AccessDeniedException을 발생함.