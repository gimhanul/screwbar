### 2-5-1. Spring Security Config

**Filter Off**

사용하지 않을 Filter를 명시적으로 disable함.

```java
http.httpBasic().disable()
```

<br>

**Login Page**

폼 로그인의 로그인 페이지를 지정하고 로그인에 성공했을 때 이동하는 url 지정함.

```java
http.formLogin()
    .loginPage("/login")
    .defaultSuccessUrl("/")
    .permitAll();
```

<br>

**Logout Page**

로그아웃 url을 지정하고 로그아웃에 성공했을 때 이동하는 url을 지정함.

```java
http.logout()
    .logoutRequestMatcher(new AntPathRequestMatcher("logout"))
    .logoutSuccessUrl("/");
```

<br>

**Authorize**

- `authorizeRequests()` : 인가를 설정함.
- `permitAll()` : 요청을 모두에게 허용함.
- `hasRole()` : 권한을 검증함.
- `authenticated()` : 인증이 되었는지를 검증함.

<br>

**Ignoring**

특정 resource에 대해서 `Spring Security를 적용하고 싶지 않을 때` 사용함.

permitAll()을 사용한 코드와는 다르게 아예 Spring Security를 사용하지 않기 때문에, 어떤 filter도 실행되지 않아서 성능이 우수함.

```java
web.ignoring().requestMatchers(PathRequest.toStaticResources().atCommonLocations());
```