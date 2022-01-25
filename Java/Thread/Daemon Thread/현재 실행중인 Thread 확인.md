### 10-5-2. 현재 실행중인 Thread 확인

현재 실행 중인 스레드가 데몬 스레드인지 아닌지를 구별하려면 isDaemon() 메소드의 return값을 조사함. 데몬스레드일 때 true를 return함.

```java
thread.isDaemon()
```

👉🏻 [예제](https://github.com/gimhanul/Java/tree/master/src/thread/daemon)