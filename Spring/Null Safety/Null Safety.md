## 1-7. Null Safety

null 안정성을 높이는 방법.

- 아래와 같은 코드를 만들지 않는 방법.
- 혹은 아래와 같은 null check를 하지 않아서 발생하는 NPE(NullPointerException)을 방지하는 방법.
- 완벽한 방법은 아니지만 IDE(Intellij, Eclipse)에서 경고를 표시함으로써 1차적인 문제를 방지하고, 정확한 에러 위치를 확인할 수 있도록 도움.

```java
public void method(String request) {
    if(request == null) return;

    System.out.println(request.toUpperCase());
}
```