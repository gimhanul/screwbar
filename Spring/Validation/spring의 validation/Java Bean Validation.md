**1-3-2-1. Java Bean Validation**

JavaBean 기반으로 간편하게 개별 데이터를 검증

JavaBean 내에 annotation으로 검증 방법을 명시함.

```java
public class MemberCreationRequest {
	@NotBlank(message="이름을 입력해주세요")
	@Size(max=64, mesage="이름의 최대 길이는 64자입니다.")
	private String name;
	
	@Min(0, "나이는 0보다 커야 합니다.")
	private int age;
	
	@Email("이메일 형식이 잘못되었습니다.")
	private String int email;

	//the usual getters and setters
}
```

위처럼 요청 DTO에 annotation으로 명시 후 `@Valid` annotation을 해당 `@RequestBody`에 달게 되면, Java Bean Validation을 수행한 후 문제가 없을 때만 메소드 내부로 진입함.

```java
@PostMapping(value = "/member")
public MemberCreateionResponse createMember (
	@Valid @RequestBody final MemberCreationRequest memberCreationRequest) {
	//member creation logics
}
```

> 👉🏻 검증 중 실패가 발생하면 MethodArgumentNotValidException 발생