### 12-12-1. System.in 필드

System.in 은 InputStream 타입의 필드로 InputStream 변수로 참조가 가능함.

```java
InputStream is = System.in;
```

어떤 키가 입력되었는지 확인하려면 InputStream의 read() 메소드로 1byte를 읽으면 됨. 리턴된 int 값에는 해당 키의 코드가 저장되어 있음.

```java
int keyCode = is.read();
```

<br>

**Enter 키가 입력되고 나서 라인 단위로 전체 문자열을 읽는 방법**

```java
InputStream is = System.in;
Reader reader = new InputStreamReader(is);
BufferedReader br = new BufferedReader(reader);
```

위와 같이 보조 스트림을 연결하고, BufferedReader의 `readLine()` 메소드를 이용할 수 있음.

```java
String lineStr = br.readLine();
```

👉🏻 [예제](https://github.com/gimhanul/Java/blob/master/src/input_output_api/GetLineStringFromKeyboard.java)