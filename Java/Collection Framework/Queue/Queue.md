## 11-5. Queue


FIFO(First In First Out) 자료구조를 구현한 클래스.

Queue 인터페이스를 구현한 대표적인 클래스는 LinkedList이므로 다음과 같이 생성함.

```java
Queue<E> queue = new LinkedList<E>();
Queue<E> queue = new LinkedList<>();
```

> 👉🏻 두 번째 코드와 같이 LinkedList의 E 타입 파라미터를 생략하면 왼쪽 Queue에 지정된 타입을 따라감.