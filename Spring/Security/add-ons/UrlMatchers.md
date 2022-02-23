### 2-5-2. UrlMatchers

- antMatchers

```java
http.authorizeRequests()
    .antmatchers("/signup").permitAll()
```

"/signup" 요청을 모두에게 허용.

<br>

- mvcMatchers

```java
http.authorizeRequests()
    .mvcMatchers("/signup").permitAll()
```

"/signup", "/signup/", "/signup.html" 과 같은 유사 signup 요청을 모두에게 허용함.

<br>

- regexMatcher

정규 표현식으로 매칭함.

<br>

- requestMatchers

antMatchers, mvcMatchers, regexMatchers는 결국에 requestMatchers로 이루어져 있음. 

명확하게 요청 대상을 지정하는 경우 사용함.