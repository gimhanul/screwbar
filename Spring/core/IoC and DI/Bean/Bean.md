### 1-1-1. Bean이란?

- java의 Bean → javaBean
    
    데이터를 저장하기 위한 구조체. (동작을 수행하기 위한 용도 X)
    
    자바 빈 규약을 따름.
    
    private 프로퍼티와 getter/setter로만 데이터에 접근함.
    
- spring의 Bean
    
    `spring IoC Container`에 의해 생성되고 관리되는 객체.
    
    java에서처럼 new Object(); 로 생성하는 것이 아님.
    
    spring IoC Container에는 Spring Application Context가 있음.
    
    이 Spring Application Context에게 내가 만든 class를 Bean으로 등록해줘! 하면 얘가 나름대로 설정을 입혀서 Bean으로 등록함. → IoC Container에 담김.
    
    각각의 Bean들끼리 서로 편리하게 의존(사용) 할 수 있음.