## 7-3. Nested Interface


클래스의 멤버로 선언된 인터페이스. 클래스와 긴밀한 관계를 맺는 구현 클래스를 만들기 위해 사용함.

```java
class A {
	[static] interface I {
		void method();
	}
}
```