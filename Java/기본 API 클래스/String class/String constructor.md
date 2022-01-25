### 9-4-1. String 생성자

자바의 문자열은 java.lang 패키지의 String 클래스의 인스턴스로 관리됨. 소스상에서 문자열 리터럴은 String 객체로 자동 생성되지만, String 클래스의 다양한 생성자를 이용해 직접 String 객체를 생성할 수 있음.

```java
//배열 전체를 String 객체로 생성
String str = new String(byte[] bytes);
//지정한 문자셋으로 디코딩
String str = new String(byte[] bytes, String charsetName);

//배열의 offset 인덱스 위치부터 length만큼 String 객체로 생성
String str = new String(byte[] bytes, int offset, int length);
//지정한 문자셋으로 디코딩
String str = new String(byte[] bytes, int offset, int length, String charsetName);
```

> 👉🏻 파일의 내용을 읽거나, 네트워크를 통해 받은 데이터는 보통 byte[] 배열이므로 이것을 문자열로 변환하기 위해 사용됨.


👉🏻 [예제](https://github.com/gimhanul/Java/tree/master/src/basic_api_class/string/constructor)