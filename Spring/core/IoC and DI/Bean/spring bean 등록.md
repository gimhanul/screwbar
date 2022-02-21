### 1-1-2. Spring Bean 등록

과거에는 XML 로 설정을 따로 등록했음(불편)

현재는 annotation 기반으로 등록함.

→ @Bean, @Container, @Service

- Bean 등록 시 정보
    - Class 경로
    - Bean의 이름
        
        default로는 클래스 이름의 앞글자만 소문자로 변경해서 만듦.
        
        → 원하는 경우 변경 가능.
        
    - Scope (Bean 생성 규칙)
        - singleton : container에 단일로 생성. (안 변함)
        - prototype : 작업시마다 새로 생성.
        - request : http 요청마다 새로 생성.
        
    - Bean LifeCycle callback
        - callback : 어떤 이벤트가 발생하는 경우 호출하는 메소드.
        - LifeCycle callback : Bean을 생성하고 초기화하고 파괴하는 등 특정시점에 호출되도록 정의한 메소드.
        - 주로 많이 사용되는 callback
            - @PostConstruct : Bean 생성 시점에 필요한 작업을 수행.
            - @PreDestroy : Bean 파괴(주로 application 종료) 시점에 필요한 작업을 수행.
