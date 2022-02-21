### 2-2-1. ThreadLocal

WebMVC 기반으로 project를 만든다고 가정할 때,
`요청 한 개당 Thread 한 개가 생성`됨.

이때 ThreadLocal을 사용하면, Thread 마다 고유한 공간을 만들 수 있고, 그곳에 SecurityContext를 저장할 수 있음.

- ThreadLocal로 SecurityContext를 관리하면, SecurityContext는 요청마다 독립적으로 관리됨.

- `InheritableThreadSecurityLocalSecurityContextHolderStrategy` 를 사용함.