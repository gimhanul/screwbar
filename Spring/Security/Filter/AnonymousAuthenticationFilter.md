### 2-4-6. AnonymousAuthenticationFilter

인증이 안 된 유저가 요청을 하면 `Anonymous User`로 만들어서 anonymous user token을  Authentication에 넣어줌.

> 인증되지 않았다고 하더라도 null을 넣는 게 아니라 기본 Authentication을 만들어줌.

다른 Filter에서 Anonymous User인지 인증된 User인지 분기 처리를 할 수 있음.

<br>

다음과 같이 활성화함.

```java
// SpringSecurityConfig.java

@Override
protected void configure(HttpSecurity http) throws Exception {
    http.anonymous().principal("anonymousUser");
    // principal 없어도 됨. 이름 지정 st.
}
```
