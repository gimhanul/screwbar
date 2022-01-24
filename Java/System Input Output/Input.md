## 2-2. Input


```java
System.in.read();
```

시스템에서 입력된 keyCode를 `하나씩` 읽음.

`Enter`가 입력될 때까지 console창이 대기 상태가 됨.

하지만, KeyCode를 하나씩 읽기 때문에 2개 이상의 키가 조합된 한글은 읽을 수 없음.

이러한 단점을 보완하기 위해 `Scanner Class`를 사용함.

```java
import java.util.Scanner;

Scanner scanner = new Scanner(System.in); //Scanner 변수 선언
String inputData = scanner.nextLine(); //Enter 입력 이전의 문자열 읽음
```