### 2-4-2. BasicAuthenticationFilter

login을 하지 않아도, id와 password를 Base64로 인코딩해서 모든 요청에 포함해서 보내면 BasicAuthenticationFilter가 이를 인증함.

- session이 필요 없고, `요청이 올 때마다` 인증이 이루어짐.
    > stateless함. == 상태를 저장하지 않음.
- 요청할 때마다 id와 password가 반복해서 노출되기 때문에 `보안에 취약`함.
    > 이 Filter를 사용할 때는 반드시 https를 사용하도록 권장됨.

<br>

다음과 같이 비활성화함.

```java
// SpringSecurityConfig.java

@Override
protected void configure(HttpSecurity http) throws Exception {
    http.httpBasic().dissable();
}

```