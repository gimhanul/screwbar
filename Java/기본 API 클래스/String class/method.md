### 9-4-2. String Method

- `charAt()` [-문자 추출](https://github.com/gimhanul/Java/tree/master/src/basic_api_class/string/method/StringCharAtTest.java)
    
    매개값으로 주어진 인덱스의 문자를 return함.

<br>
 
- `equals()` [-문자열 비교](https://github.com/gimhanul/Java/tree/master/src/basic_api_class/string/method/StringEqualsTest.java)
    
    문자열의 내용을 비교함.

<br>
 
    
- `getBytes()` [-바이트 배열로 변환](https://github.com/gimhanul/Java/tree/master/src/basic_api_class/string/method/StringGetBytesTest.java)
    
    문자열을 바이트 배열로 변환함. 네트워크로 문자열을 전송하거나 문자열을 암호화할 때 문자열을 바이트 배열로 변환하는 경우가 있음. 매개변수로 Charset을 넣어서 특정 문자셋으로 인코딩할 수 있음.

<br>
 
    
- `indexOf()` [-문자열 찾기](https://github.com/gimhanul/Java/tree/master/src/basic_api_class/string/method/StringIndexOfTest.java)
    
    매개값으로 주어진 문자열이 시작되는 인덱스를 return함. 주어진 문자열이 포함되어 있지 않으면 -1을 return함.
    
    밑과 같이 특정 문자열이 포함되어 있는지를 확인할 때 자주 사용함.
    
    ```java
    if(문자열.indexOf("찾는문자열") != -1) {
    	//포함되어 있는 경우
    } else {
    	//포함되어 있지 않은 경우
    }
    ```

<br>
 
    
- `length()` [-문자열 길이](https://github.com/gimhanul/Java/tree/master/src/basic_api_class/string/method/StringLengthTest.java)
    
    문자열의 길이(문자의 수)를 return함.

<br>
 
    
- `replace()` [-문자열 대치](https://github.com/gimhanul/Java/tree/master/src/basic_api_class/string/method/StringReplaceTest.java)
    
    첫 번째 매개값인 문자열을 찾아 두 번째 매개값인 문자열로 대치한 새로운 문자열을 생성하고 return함.

<br>
 
    
- `substring()` [-문자열 잘라내기](https://github.com/gimhanul/Java/tree/master/src/basic_api_class/string/method/StringSubstringTest.java)
    
    주어진 인덱스에서 문자열을 추출함. 매개변수를 두 개 넣으면 그 사이의 문자열을 추출하고, 한 개 넣으면 주어진 인덱스부터 끝까지의 문자열을 추출함.

<br>
 
    
- `toLowerCase()`, `toUpperCase()` [-알파벳 대소문자 변경](https://github.com/gimhanul/Java/tree/master/src/basic_api_class/string/method/StringToLowerUpperCaseTest.java)
    
    toLowerCase()는 문자열을 모두 소문자로 바꾼 새로운 문자열을 생성한 후 return함.
    
    toUpperCase()는 문자열을 모두 대문자로 바꾼 새로운 문자열을 생성한 후 return함. 
    
    영어로 된 두 문자열을 대소문자와 관계없이 비교할 때 주로 이용됨. →  `equalsIgnoreCase()` 메소드를 사용하면 이 작업마저도 필요 없음.

<br>
 
    

- `trim()` [-문자열 앞뒤 공백 잘라내기](https://github.com/gimhanul/Java/tree/master/src/basic_api_class/string/method/StringTrimTest.java)
    
    문자열의 앞뒤 공백을 제거한 새로운 문자열을 생성하고 return함.

<br>
 
    
- `valueOf()` [-문자열 변환](https://github.com/gimhanul/Java/tree/master/src/basic_api_class/string/method/StringValueOfTest.java)
    
    기본 타입의 값을 문자열로 변환함. 
    
    String 클래스에는 매개 변수의 타입별로 valueOf() 메소드가 다음과 같이 오버로딩되어 있음.
    
    ```java
    static String valueOf(boolean b)
    static String valueOf(char c)
    static String valueOf(int i)
    static String valueOf(long l)
    static String valueOf(double d)
    static String valueOf(float f)
    ```