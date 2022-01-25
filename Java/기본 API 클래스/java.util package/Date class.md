### 9-7-1. Date 클래스

특정 시점의 날짜를 표현하는 클래스. Date 객체 안에는 특정 시점의 연도, 월, 일 시간 정보가 저장됨. 

현재 시각의 Date 객체는 다음과 같이 생성할 수 있음.

```java
Date now = new Date();
```

Date 객체의 toString() 메소드는 영문으로 된 날짜를 return함.

원하는 날짜 형식의 문자열을 얻고 싶다면 java.text 패키지의 `SimpleDateFomat` 클래스와 함께 사용함.

원하는 형식 문자열로 SimpleDateFomat을 다음과 같이 생성할 수 있음.

```java
SimpleDateFomat sdf = new SimpleDateFormat("yyyy년 MM월 dd일 hh시 mm분 ss초");
```

SimpleDateFormat 객체를 얻었다면, `format()` 메소드를 호출해서 원하는 형식의 날짜 정보를 얻을 수 있음. format() 메소드의 매개값은 Date 객체임.

```java
String strNow = sdf.format(now);
```