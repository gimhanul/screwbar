### 12-7-1. OutputStreamWriter

OutputStreamWriter는 바이트 기반 출력 스트림에 연결되어 문자 출력 스트림인 Writer로 변환하는 보조 스트림임.

```java
Writer writer = new OutputStreamWriter(바이트 기반 출력 스트림);
```