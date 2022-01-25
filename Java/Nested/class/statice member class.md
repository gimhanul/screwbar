### 7-1-3. 정적 멤버 클래스

`static` 키워드로 선언된 클래스.

<br>

**특징**

- 모든 종류의 필드와 메소드를 선언할 수 있음.

<br>

**생성**

바깥 클래스를 A, 내부 클래스를 B라고 했을 때 B 클래스를 생성하려면

A 객체를 생성할 필요가 없고 다음과 같이 생성함.

```java
A.B b = nw A.B();
b.field1 = 3;
b.method1();
```