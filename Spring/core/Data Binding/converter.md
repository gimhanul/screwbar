### 1-4-1. Converter

**Converter<S, T> Interface**

S(Source) 타입에서 T(Target) 타입으로 변환해주는 Interface

```java
package org.springframework.core.convert.converter;

public interface Convert<S, T> {
	T convert(S source);
}
```

**데이터를 특정 object에 담고 싶은 경우**

PathParameter, RequestBody 등 기타 특수한 경우

- ConversionService라는 Spring에 내장된 서비스에서 Converter 구현체 Bean들을 Converter List에 등록함.
- 외부 데이터가 들어오고, Source Class Type → Target Class Type이 Converter에 등록된 형식과 일치하면 해당 Converter가 자동으로 동작함.

- 파라미터에 json 형식 문자열이 담겨오는 경우 해당 문자열을 특정 DTO에 담기
    
    ```java
    GET /user-info
    x-auth-user : {"id":123, "name":"Paul"}
    
    //User Object
    public class XAuthUser {
    	private int id;
    	private String name;
    }
    
    @GetMapping("/user-info")
    public UserInfoResponse getUserInfo(
    	@RequestHeader("x-auth-user") XAuthUser xAuthUser) {
    	
    	//get User Info logic
    }
    ```
    <br>
    <br>
    
    ---

    헤더에 담긴 json 형식 문자열을 XAuthUser에 바로 담고 싶은 경우 아래와 같이 Converter를 Bean으로 등록함.
    
    ```java
    @Component
    public class XAuthUserConverter implements Converter<String, XAuthUser> {
    	@Override
    	public XAuthUser convert(String source) {
    		return objectMapper.readValue(source, XAuthUser.class);
    	}
    }
    ```