### 2-4-5. RememberMeAuthenticationFilter

`로그인을 장시간 유지`하도록 함.

remember-me cookie를 사용해서 login session이 만료하더라도, login session을 다시 연결 시켜줌. (로그인 유지 st)

session 만료 시간의 기본값은 30분이지만 RememberMeAuthenticationFilter의 기본 설정은 2주임.

<br>

기본적으로 꺼져 있으며, 다음과 같이 세팅할 수 있음.

```java
// SpringSecurityConfig.java

@Override
protected void configure(HttpSecurity http) throws Exception {
    http.rememberMe();
}
```