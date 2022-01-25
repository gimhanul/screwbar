### 11-3-4. HashTable

HashTable은 다음과 같이 생성함.

```java
Map<K, V> map = new HashTable<K, V>();
Map<K, V> map = new HashTable<>();
```

> 👉🏻 두 번째 코드와 같이 HashMap의 K, V 타입 파라미터를 생략하면 왼쪽 Map에 지정된 타입을 따라감.

<br>

- HashMap과 동일한 내부 구조를 가짐.
- 하지만, HashMap과는 다르게 동기화된 메소드로 구성되어 있기 때문에 멀티 스레드가 동시에 HashTable의 메소드들을 실행할 수 없음.
- 멀티 스레드 환경에서 안전하게 객체를 추가, 삭제할 수 있음.
    
    → 이를 스레드에 안전 `thread safe` 하다고 표현함.
    