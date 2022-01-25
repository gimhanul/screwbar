### 1-6-1. SpEL의 값 평가(evaluation)

```java
ExpressionParser parser = new SpelExpressionParser();
Expression exp = parser.parseExpression("'Hello World'");
String message = (String) exp.getValue(); //"Hello World"

Expression expWow = parser.parseExpression("'Hello World'.concat('!')"); //concat은 뒤에 ! 붙이는 거.
String messageWow = (String) expWow.getValue(); //"Hello World!"

Expression expString = parser.parseExpression("new String('hello world').toUpperCase()");
String messageString = expString.getValue(String.class); //"HELLO WORLD"
```

- SpelParser는 "" 안에 들어있는 문자열을 evaluation(평가)해서 결과값을 만들어냄.
- "Hello World"는 문자열 리터럴이 되며, concat이라는 메소드를 호출할 수 있음.
- String 객체를 생성해서 사용할 수 있음.