### 1-6-2. Bean의 Property를 설정할 때 사용하는 방식

- 기본적으로 `#{ <expression string> }` 방식으로 property를 설정함.
- application.properties(또는 application.yml)의 값을 가져올 때는 `${ <property name> }` 방식으로 가져옮.

``` java
@Component
public class SimpleComponent {
    @Value("#{ 1+1 }")
    int two; //2

    @Value("#{ 2 eq 2 }")
    boolean isTrue; //true

    @Value("${ server.hostname }")
    String hostName; //www.server.com

    @Value("#{ ${ server.hostname } eq 'www.server.com' }")
    boolean isMostSame; //true
}
```

> 👉🏻 주로 운영 환경과 테스트 환경을 분리할 때 사용함.