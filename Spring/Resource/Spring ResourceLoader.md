### 1-5-2. Spring ResourceLoader
spring project 내 Resource에 접근할 때 사용하는 기술.

-> Resource 구현체를 사용함.

- 기본적으로 applicationContext에서 구현되어 있음.
- 프로젝트내 파일(주로 classpath 하위 파일)에 접근할 일이 있을 경우 활용함.
- 대부분의 사전정의된 파일들은 자동으로 로딩됨. 하지만, 추가로 필요한 파일이 있을 때 활용.

```java
@Service
public class ResourceService {
    @Autowired //자동으로 dependency를 받음. 자기 자신을 injection(삽입)함.
    ApplicationContext ctx;

    public void setResource() {
        Resource myTemplate = ctx.getResource("classpath:some/resource/path/myTemplate.txt");
            //ctx.getResource("file:/some/resource/path/myTemplae.txt);
            //ctx.getResource("http://myhost.com/resource/path/myTemplate.txt);
        
        //use myTemplate
    }
}
```


