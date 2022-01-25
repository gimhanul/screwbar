### 10-3-2. Thread 하위 클래스로부터 생성

작업 스레드가 실행할 작업을 Runnable로 만들지 않고, Thread의 하위 클래스로 작업 스레드를 정의하면서 작업 내용을 포함시킬 수 있음.

작업 스레드 클래스를 정의함. Thread 클래스를 상속한 후 run() 메소드를 overriding해서 스레드가 실행할 코드를 작성함. 작업 스레드 클래스로부터 작업 스레드 객체를 생성하는 방법은 일반적인 객체 생성 방법과 동일함.

```java
public class WorkerThred extends Thread {
	@Override
	public void run() {
		//스레드가 실행할 코드
	}
}

Thread thread = new WorkerThread();
```

> 👉🏻 코드를 절약하기 위해 Thread 익명 객체로 작업 스레드 객체를 생성할 수도 있음.

<br>

이렇게 생성된 작업 스레드 객체에서 start() 메소드를 호출하면 작업 스레드는 자신의 run()메소드를 실행함.

👉🏻 [예제](https://github.com/gimhanul/Java/tree/master/src/thread/extends_thread)