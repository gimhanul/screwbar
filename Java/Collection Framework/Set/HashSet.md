### 11-2-3. HashSet

HashSet를 생성하기 위해서 저장할 객체 타입을 E 타입 파라미터에 표기하고 기본 생성자를 호출함.

```java
Set<E> set = new HashSet<E>();
Set<E> set = new HashSet<>();
```

> 👉🏻 두 번째 코드와 같이 LinkedList의 E 타입 파라미터를 생략하면 왼쪽 Set에 지정된 타입을 따라감.

<br>


- 객체들을 순서 없이 저장하고 동일한 객체는 중복 저장하지 않음.
- HastSet이 판단하는 동일한 객체란 꼭 같은 인스턴스를 뜻하지는 않음.
- HastSet은 객체를 저장하기 전 먼저 객체의 HashCode()메소드를 호출해서 해시코드를 얻어내고, 이미 저장되어 있는 객체들의 해시코드와 비교함.
- 동일한 해시코드가 있다면 다시 equals() 메소드로 두 객체를 비교해서 true가 나오면 동일한 객체로 판단하고 중복 저장을 하지 않음.

👉🏻 [예제](https://github.com/gimhanul/Java/tree/master/src/collection_framework/set)