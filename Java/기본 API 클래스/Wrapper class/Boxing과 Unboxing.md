### 9-5-2. Boxing과 Unboxing

기본 타입의 값을 포장 객체로 만드는 과정을 `Boxing`이라고 함.

포장 객체에서 기본 타입의 값을 얻어내는 과정을 `Unboxing`이라고 함.

<br>
 
- **Boxing**

👇🏻 포장 클래스의 생성자 매개값으로 기본 타입의 값 또는 문자열을 넘겨주면 됨.

```java
Integer obj = new Integer(1000);
Integer obj = new Integer("1000");
```

👇🏻 각 포장 클래스마다 가지고 있는 정적 valueOf() 메소드를 사용할 수 있음.

```java
Integer obj = Integer.valueOf(1000);
Integer obj = Integer.valueOf("1000");
```

<br>
 
- **Unboxing**

다시 기본 타입의 값을 얻어내기 위해서는 각 포장 클래스마다 가지고 있는 기본 타입 이름 + Value() 메소드를 호출하면 됨.

```java
int num = obj.intValue();
```