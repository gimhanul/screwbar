### 2-5-4. Custom Filter

Custom Filter를 구현하기 위해서는 Filter Interface를 구현하면 됨.

그러나 이를 직접 구현하면, 중복 실행 문제가 있어, `OncePerRequestFilter`를 구현하기를 권장함.

**순서**

1. Filter 구현

2. SpringSecurityConfig.java에서 Custom Filter 위치 지정

```java
http.addFilterBefore(
    new CustomFilter(),
    WebAsyncManagerIntegrationFilter.class
);
```

