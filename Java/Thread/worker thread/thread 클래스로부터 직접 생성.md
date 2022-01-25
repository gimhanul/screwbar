### 10-3-1. Thread 클래스로부터 직접 생성

java.lang.Thread 클래스로부터 작업 스레드를 직접 생성하려면, Runnable을 매개값으로 갖는 생성자를 호출해야함.

```java
Thread thread = new Thread(Runnable target);
```

`Runnable`은 작업 스레드가 실행할 수 있는 코드를 가지고 있는 객체임. 인터페이스 타입이며, 구현 객체를 만들어 대입해야 함.

Runnable에는 run() 메소드가 하나 정의되어 있어, 구현 클래스는 run()을 재정의 해서 작업 스레드가 실행할 코드를 작성해야함.

다음과 같이 작성함.

```java
class Task implements Runnable {
	@Override
	public void run() {
		//스레드가 실행할 코드;
	}
}
```

> 👉🏻 코드를 절약하기 위해 Thread 생성자를 호출할 때 Runnable 익명 객체를 매개값으로 사용할 수 있음. 오히려 이 방법이 더 많이 사용됨.

<br>

작업 스레드 생성을 해도 즉시 실행되지 않고, `start()` 메소드를 호출하여 실행함.

해당 메소드가 호출되면, 작업 스레드는 Runnable의 run()메소드를 실행하면서 작업을 처리함.

```java
thread.start();
```

👉🏻 [예제](https://github.com/gimhanul/Java/tree/master/src/thread/thread_class)