### 1-5-4. applicationContext and Resource Paths

applicationContext(Spring의 핵심 설정)을 이루는 설정값을 가져오는 방법들

```java
//create applicationContext
ApplicationContext ctx = new ClassPathXmlApplicationContext("conf/appContext.xml");

ApplicationContext ctx = new FileSystemXmlApplicationContext("conf/appContext.xml");

ApplicationContext ctx = new FileSystemXmlApplicationContext("classpath:conf/appContext.xml");

//then use
Bear bear = (Bear) ctx.getBean("bear");
```

> 👉🏻 XML 사용하는 건 다 과거. 요즘은 그냥 annotation 기반으로 설정값을 잡음.