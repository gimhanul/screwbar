### 5-5-5. instanceof 연산자

객체가 `어떤 클래스의 인스턴스인지 확인`하기 위해 instanceof 연산자를 사용함.

```java
boolean result = 좌항(객체) instanceof 우항(타입)
```

좌항의 객체가 우항의 인스턴스이면, → 즉 우항의 타입으로 객체가 생성되었다면 true 를 return함.

메소드 내에서 강제 타입 변환이 필요할 경우 반드시 매개값이 어떤 객체인지 instanceof 연산자로 확인하고 안전하게 casting을 해야 함.

👉🏻 [예제](https://github.com/gimhanul/Java/tree/master/src/inheritance/polymorphism/instanceov)