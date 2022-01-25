### 10-5-1. Daemon Thread 지정

스레드를 데몬 스레드로 만들기 위해서는 주 스레드가 데몬이 될 스레드의 setDaemon(true)를 호출함.

```java
thread.setDaemon(true);
thread.start();
```

> 👉🏻 반드시 start() 메소드를 호출하기 전에 호출해야 함. → 그렇지 않으면 IllegalThreadStateException 발생.