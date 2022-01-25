### 12-8-2. BufferedInputStream과 BufferedReader

BufferedInputStream은 바이트 기반 입력 스트림에 연결되어 버퍼를 제공함.

BufferedReader는 문자 기반 입력 스트림에 연결되어 버퍼를 제공함.

입력 버퍼는 입력 소스로부터 자신의 내부 버퍼 크기만큼 데이터를 `미리 읽고 버퍼에 저장`해둠.

프로그램은 외부의 입력 소스로부터 직접 읽는 대신 버퍼로부터 읽음으로써 읽기 성능이 향상됨.

```java
BufferedInputStream bis = new BufferedInputStream(바이트 기반 입력 스트림);
BufferedReader br = new BufferedReader(문자 기반 입력 스트림);
```

<br>

추가로, BufferReader는 라인 단위로 문자열을 읽는 매우 편리한 [readLilne()](https://github.com/gimhanul/Java/tree/master/src/input_ouput_stream/sub_stream/buffer/ReadLineTest.java) 메소드를 제공함.

readLine()은 Enter 키(개리지 리턴(\r) + 라인피드(\n)) 이전의 모든 문자열을 읽고 return함.

더 이상 읽을 라인이 없다면 null을 return함.

👉🏻 [예제](https://github.com/gimhanul/Java/tree/master/src/input_ouput_stream/sub_stream/buffer/BufferedStreamTest.java)