### 4-8-4. Constructor Overloading

매개변수를 달리하는 생성자를 여러 개 선언하는 것.

```java
public class Car() {
	Car() { ··· }
	Car(String model) { ··· }
	Car(String model, String color) { ··· }
	Car(String model, String color, int maxSpeed) { ··· }
}
```