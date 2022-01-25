### 11-1-3. ArrayList

ArrayList를 생성하기 위해서는 저장할 객체 타입을 E 타입 파라미터 자리에 표기하고 기본 생성자를 호출함.

```java
List<E> list = new ArrayList<E>();
List<E> list = new ArrayList<>();
```

> 👉🏻 두 번째 코드와 같이 ArrayList의 E 타입 파라미터를 생략하면 왼쪽 List에 지정된 타입을 따라감.

<br>

- ArrayList는 내부 배열에 객체를 저장해서 관리함.
- ArrayList는 생성했을 때 초기 용량을 10으로 가짐. 여기서 저장되는 객체 수가 늘어나면 용량이 자동으로 증가함.
- 특정 객체를 제거하면 바로 뒤 인덱스부터 마지막 인덱스까지 모두 앞으로 1씩 당기고, 중간에 삽입하면 뒤 인덱스부터 마지막 인덱스까지 모두 뒤로 1씩 밀어냄.
- 이런 동작 때문에 특정 인덱스에 객체를 추가하거나 제거하는 일이 빈번하다면 사용하지 않음.
    
    → linkedList 사용
    
- 인덱스를 이용해 객체를 찾거나 맨 마지막에 객체를 추가하는 경우 이용함.

👉🏻 [예제](https://github.com/gimhanul/Java/tree/master/src/collection_framework/list/ArrayListTest.java)