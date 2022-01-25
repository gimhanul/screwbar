### 12-11-4. Serializable Interface

자바는 모든 객체를 직렬화하지 않음. java.io.Serializable 인터페이스를 구현한 객체만 직렬화함.

Serializable 인터페이스는 메소드 선언이 없는 인터페이스임.

객체를 파일로 저장하거나, 네트워크로 전송할 목적이라면 클래스를 선언할 때 implements를 해야 함.

👉🏻 [예제](https://github.com/gimhanul/Java/tree/master/src/input_ouput_stream/sub_stream/object)