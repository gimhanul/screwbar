### 10-3-3. Thread Name

스레드는 자신의 이름을 가짐. 이름이 큰 역할을 하지는 않지만, 디버깅 할 때 어떤 스레드가 어떤 작업을 하는지 조사할 목적으로 가끔 사용함. 기본적으로 스레드는 자동적으로 `Thread-n` 이라는 이름으로 설정됨. (n은 스레드의 번호)

`setName()` 메소드로 Thread의 이름을 변경할 수 있음.

```java
thread.setName("스레드 이름");
```

`getName()` 메소드로 Thread의 이름을 알 수 있음.

```java
thread.getName();
```

setName과 getName은 스레드 객체의 참조가 필요함. 만약 스레드 객체의 참조가 없다면, Thread 클래스의 정적 메소드인 `currentThread()` 를 이용해서 현재 스레드의 참조를 얻을 수 있음.

```java
Thread thread = Thread.currentThread();
```