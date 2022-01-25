### 11-3-3. HashMap

HashMap은 다음과 같이 생성함.

```java
Map<K, V> map = new HashMap<K, V>();
Map<K, V> map = new HashMap<>();
```

> 👉🏻 두 번째 코드와 같이 HashMap의 K, V 타입 파라미터를 생략하면 왼쪽 Map에 지정된 타입을 따라감.

<br>

key로 사용할 객체는

- 객체가 달라도 동등 객체라면 같은 키로 간주하고 중복 저장하지 않아야 함.
- hashCode()와 equals() 메소드를 재정의해서 동등 객체가 될 조건을 정함.
- 동등 객체의 조건은 hashCode()의 return 값이 같아야 함.
- equals() 메소드가 true를 return해야 함.

👉🏻 [예제](https://github.com/gimhanul/Java/tree/master/src/collection_framework/map/hash_map)
