### 11-1-4. Vector

Vector를 생성하기 위해서는 저장할 객체 타입을 E 타입 파라미터로 표기하고 기본 생성자를 호출함.

```java
List<E> list = new Vector<E>();
List<E> list = new Vector<>();
```

> 👉🏻 두 번째 코드와 같이 Vector의 E 타입 파라미터를 생략하면 왼쪽 List에 지정된 타입을 따라감.

<br>

- ArrayList와 동일한 내부 구조를 가짐.
- 하지만, ArrayList와는 다르게 동기화된 메소드로 구성되어 있기 때문에 멀티 스레드가 동시에 Vector의 메소드들을 실행할 수 없음.
- 멀티 스레드 환경에서 안전하게 객체를 추가, 삭제할 수 있음.
    
    → 이를 스레드에 안전 `thread safe` 하다고 표현함.