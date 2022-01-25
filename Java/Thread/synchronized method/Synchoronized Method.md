### 10-4-2. Synchoronized Method

동기화 메소드. 스레드가 사용 중인 객체를 다른 스레드가 변경할 수 없게 하려면 스레드 작업이 끝날 때까지 객체에 잠금을 걸어서 다른 스레드가 사용할 수 없도록 해야함.

멀티 스레드 프로그램에서 단 하나의 스레드만 실행할 수 있는 코드 영역을 `critical section` (임계 영역)이라고 함.

자바는 critical section을 지정하기 위해 동기화 메소드를 제공함.

스레드가 객체 내부의 동기화 메소드를 실행하면 즉시 객체에 잠금을 걸어 다른 스레드가 동기화 메소드를 실행하지 못하도록 함.

동기화 메소드를 만들려면 다음과 같이 메소드 선언에 `synchronized` 키워드를 붙임. 인스턴스와 정적 메소드 어디든 붙일 수 있음.

```java
public synchronized void method() {
	//critical section
}
```

> 👉🏻 만약 동기화 메소드가 여러 개 있을 경우, 스레드가 이들 중 하나를 실행할 때 다른 스레드는 해당 메소드는 물론이고 다른 동기화 메소드도 실행할 수 없음. 하지만, 일반 메소드는 실행 가능함.

<br>

👉🏻 [예제](https://github.com/gimhanul/Java/tree/master/src/thread/synchronized_method)