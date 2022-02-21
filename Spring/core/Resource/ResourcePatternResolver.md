### 1-5-3. ResourcePatternResolver

spring ApplicationContext에서 ResourceLoader를 불러올 때 사용하는 Interface.

위치 지정자 패턴(classpath:, file:, http:)에 따라 자동으로 Resource Loader 구현체를 선택함.

```java
public interface ApplicationContext extends EnvironmentCapable, ListableBeanFactory, MierachicalBeanFactory, MessageSource, ApplicationEvenPublisher, ResourcePatternResolver {
    //Spring ApplicationContext interface
}
```

> 👉🏻 ApplicationContext에 ResourcePatternResolver가 extends 되어 있음.