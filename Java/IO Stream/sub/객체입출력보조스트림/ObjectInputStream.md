### 12-11-3. ObjectInputStream

객체를 역직렬화함. `readObject()` 메소드는 입력 스트림에서 읽은 바이트를 역직렬화 해서 객체로 다시 복원해서 return함. 리턴 타입은 Object이기 때문에 다음과 같이 원래 타입으로 강제 변환해야 함.

```java
객체타입 변수 = (객체타입) ois.readObject();
```