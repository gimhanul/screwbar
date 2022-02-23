### 2-5-3. Spring Security Test

Spring Security를 사용하는 project에서는 test를 진행할 때 User가 login한 상태를 가정하고 test해야 하는 경우가 많음.

이때, Spring-security-test를 사용해 Mock User를 인증시켜 놓고 test를 구동할 수 있음.

> build.gradle 에 Spring Security Test 의존성을 추가해야 함.

<br>

**setup**

test 실행 전 MockMvc에 springSecurity(static method)를 설정함.

```java
@BeforeEach
public void setup(@Autowired WebApplicationContext applicationContext) {
    this.mockMvc = MockMvcBuilders.webAppContextSetup(applicationContext)
        .apply(springSecurity()) // 이거!
        .build();
}
```

<br>

**@WithMockUser**

Mock User를 생성하고 Authentication을 만듦.

User는 org.springframework.security.core.userdetails.User임. 

> Custom User를 사용했다면 class cast error가 발생할 수 있음.

|멤버변수|예시|설명|
|--|--|--|
|roles|USER|권한, `ROLE_` 자동으로 붙음.|
|authorities|ROLE_USER|권한, 사용하면 roles를 무시함.|
|username|user123|username 지정|
|password|password123|password 지정|
|setupBefore|TestExecutionEvent.~|언제 user가 setting 되는지 정함|

<br>

**@WithUserDetails**

Mock User를 생성하고 Authentication을 만듦.

가짜 User를 가져올 때, UserDetailsService의 Bean 이름을 넣어줘서, userDetailsService.loadUserByUsername(String username)을 통해 User를 가져옮.

|멤버변수|예시|설명|
|--|--|--|
|value|user123|가져올 user의 username|
|userDetailsServiceBeanName|userDetailsService|UserDetailsService를 구현한 Bean의 이름|
|setupBefore|TestExecutionEvent.~|언제 user가 setting 되는지 정함|

<br>

**@WithAnonymousUser**

WithMockUser와 동일하지만, 인증된 유저 대신 `anonymous 유저`를 authentication에서 사용함.

익명이기 때문에 멤버 변수에 user와 관련된 값이 없음.

|멤버변수|예시|설명|
|--|--|--|
|setupBefore|TestExecutionEvent.~|언제 user가 setting 되는지 정함|

<br>

**@WithSecurityContext**

다른 방식들은 Authentication을 가짜로 만들었지만

WithSecurityContext는 아예 `SecurityContext를 만듦`.

|멤버변수|설명|
|--|--|
|factory|WithSecurityContextFactory를 Implement한 Class를 넣음.|
|setupBefore|언제 user가 setting 되는지 정함.|

<br>

**with(user(  ))**

annotation 기반이 아니라, User를 직접 MockMvc에 주입함.

WithMockUser와 마찬가지로 user를 생성해서 Principal에 넣고 Authentication을 생성해줌.

org.springframework.test.web.servlet.request.user를 사용함.

```java
mockMvc.perform(get("/admin")
            .with(user(user)))
```