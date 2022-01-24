### 4-11-4. Singleton

전체 프로그램에서 `단 하나의 객체`만 만들도록 보장해야 하는 객체

1. 생성자 앞에 `private` 접근 제한자를 붙여 외부에서 생성자 호출을 막음.

외부에서 new 연산자로 생성자를 호출할 수 없어야 함.

1. 자신의 타입인 static field를 하나 선언하고 `자신의 객체를 생성`해 초기화 함.

클래스 내부에서는 new 연산자로 생성자 호출이 가능함.

static field에도 ptivate 접근 제한자를 붙여 외부에서 값을 변경하지 못하도록 막아야 함.

1. 외부에서 호출할 수 있는 static method인 getInstance()를 선언하고 `자신의 객체를 return`함.

```java
public class 클래스 {
	//static field
	private static 클래스 singleton = new 클래스();
	
	//constructor
	private 클래스() {}
	
	//static method
	static 클래스 getInstance() {
		return singleton;
	}
}
```