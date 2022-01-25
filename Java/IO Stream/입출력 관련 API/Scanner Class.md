### 12-12-3. Scanner 클래스

Scanner 클래스는 입출력 스트림도 아니고, 보조 스트림도 아님. Scanner는 문자 파일이나 바이트 기반 입력 스트리멩서 라인 단위 문자열을 쉽게 읽도록 하기 위해 java.util 패키지에서 제공하는 클래스임.

```java
Scanner scanner = new Scanner(System.in);
String inputData = scanner.nextLine();
```

<br>

- Scanner를 생성할 때 매개변수로 바이트 기반 입력 스트림을 넣음.
- nextLine() 메소드를 사용해서 Enter 이전까지 입력된 행단위 문자열을 읽음.

👉🏻 [예제](https://github.com/gimhanul/Java/blob/master/src/input_output_api/scanner)