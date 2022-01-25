### 12-8-1. BufferedOuputStream과 BufferedWriter

BufferedOutputStream은 바이트 기반 출력 스트림에 연결되어 버퍼를 제공함.

BufferedWriter는 문자 기반 출력 스트림에 연결되어 버퍼를 제공함.

```java
BufferedOutputStream bos = new BufferedOutputStream(바이트 기반 출력 스트림);
BufferedWriter bw = new BufferedWriter(문자 기반 출력 스트림);
```