### 9-7-3. Calendar 클래스

달력을 표현한 클래스. 해당 운영체제의 Calendar 객체를 얻으면, 연도, 월, 일, 요일, 오전/오후, 시간 등의 정보를 얻을 수 있음. 

Calendar 클래스는 추상 클래스이므로 new 연산자를 사용해서 인스턴스를 생성할 수 없음. 

Calendar 클래스의 정적 메소드인 `getInstance()` 메소드를 이용하면 현재 운영체제에 설정되어 있는 시간대를 기준으로 한 Calendar 하위 객체를 얻을 수 있음.

```java
Calendar now = Calendar.getInstance();
```

객체를 얻었다면 `get()` 메소드를 이용해서 날짜와 시간에 대한 정보를 읽을 수 있음.

```java
int year = now.get(Calendar.YEAR); //년
int month = now.get(Calendar.MONTH) + 1; //월
int day = now.get(Calendar.DAY_OF_MONTH); //일
String week = now.get(Calendar.DAY_OF_WEEK); //요일
String amPm = now.get(Calendar.AM_PM); //오전 오후
int hour = now.get(Calendar.HOUR); //시
int minute = now.get(Calendar.MINUTE); //분
int second = now.get(Calendar.SECOND); //초
```