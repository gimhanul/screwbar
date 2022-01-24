**1-3-2-2. Spring validator interface 구현**

```java
public class Person {
	private String name;
	private int age;
	
	//the usual getters and setters
}
```

위처럼 Person이라는 JavaBean 객체가 있을 때, 아래는 해당 인스턴스에서만 활용되는 validator임.

인터페이스에 있는 두 개의 메소드는 아래와 같은 역할을 함.

- supports : 이 validator가 동작할 조건을 정의함. 주로 class의 타입을 비교함.
- validate : 원하는 검증을 진행함.

```java
public class PeronsalValidator implements Validator {
	public boolean supports(Class clazz) {
		return Person.class.equals(clazz);
	}

	public void validate(Object obg, Errors e) {
		ValidationUtils.rejectIfEmpty(e, "name", "name.empty");
		Person p = (Person) obj;
		
		if(p.getAge() < 0) {
			e.rejectValue("age", "negativevalue");
		} else if(p.getAge() > 110) {
			e.regectValue("age", "too.darn.ald");
		}
	}
}
```