### 9-3-1. Class 객체 얻기

1. 클래스로부터 얻는 방법

```java
Class clazz = 클래스이름.class
Class clazz = Class.forName("패키지...클래스이름")
```

1. 객체로부터 얻는 방법

```java
Class clazz = 참조변수.getClass();
```

👉🏻 [예제](https://github.com/gimhanul/Java/blob/master/src/basic_api_class/classs/ClassTest.java)