### 11-1-5. LinkedList

LinkedList를 생성하기 위해서 저장할 객체 타입을 E 타입 파라미터에 표기하고 기본 생성자를 호출함.

```java
List<E> list = new LinkedList<E>();
List<E> list = new LinkedLIst<>();
```

> 👉🏻 두 번째 코드와 같이 LinkedList의 E 타입 파라미터를 생략하면 왼쪽 List에 지정된 타입을 따라감.

<br>

- LinkedList가 처음 생성될 때에는 어떠한 링크도 만들어지지 않기 때문에 내부는 비어 있음.
- LinkedList에서 특정 인덱스의 객체를 제거할 때나 삽입할 때 하면 앞뒤 링크만 변경되고 나머지 링크는 변경되지 않음.
- 따라서 빈번한 객체 삭제와 삽입이 일어나는 곳에서는 좋은 성능을 발휘함.

👉🏻 [예제](https://github.com/gimhanul/Java/tree/master/src/collection_framework/list/LinkedListTest.java)