### 9-7-3. Optional<T>

T type의 객체를 포장해주는 Wrapper Class임.
Optional object를 사용하면 `NullPointException을 메소드로 간단히 회피`할 수 있음. 
-> 복잡한 조건문 없이도 null 값으로 인해 발생하는 예외를 처리할 수 있음.

<br>

**Optional 객체 생성**

Optional object는 of() 메소드나 ofNullable() 메소드를 사용하여 생성할 수 있음.

```java
Optional<String> opt = Optional.ofNullable("string");
System.out.println(opt.get());
```

- of() 메소드는 null이 아닌 명시된 값을 가지는 Optional 객체를 return함.
    -> 만약 null이 저장되면 NullPointException 발생.

- `ofNullable()` 메소드는 명시된 값이 null이면, 비어있는 Optional 객체를 return함.

<br>

**Optional 객체 접근**

`get()` 메소드를 사용하여 접근할 수 있음. 만약 저장된 값이 null이면, NoSuchElementException이 발생함.

- `isPresent()` 메소드를 이용해 Optional 객체에 저장된 값이 null인지 아닌지를 확인한 후 호출하는 것이 좋음.

- 혹은 다음 메소드를 사용하여 `null 대체값`을 지정할 수 있음.
    - `orElse()` : 값이 존재하지 않으면 인수로 전달된 값을 반환함.
    - `orElseGet()`: 값이 존재하지 않으면 인수로 전달된 lambda 식의 결과 값을 반환함.
    - `orElseThrow()` : 값이 존재하지 않으면 인수로 전달된 예외를 발생시킴.

<br>

**method**

![image](https://user-images.githubusercontent.com/80656733/152784730-27b013c8-d62d-4228-9beb-48820ff760f4.png)
