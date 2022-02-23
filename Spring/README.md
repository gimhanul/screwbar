# Spring



## 1. Spring의 핵심 기술

- 1-1. [IoC and DI](https://github.com/gimhanul/TIL/blob/master/Spring/core/IoC%20and%20DI/IoC%20and%20DI.md)
    - 1-1-1. [Bean이란?](https://github.com/gimhanul/TIL/blob/master/Spring/core/IoC%20and%20DI/Bean/Bean.md)
    - 1-1-2. [Spring Bean 등록](https://github.com/gimhanul/TIL/blob/master/Spring/core/IoC%20and%20DI/Bean/spring%20bean%20%EB%93%B1%EB%A1%9D.md)
- 1-2. [Aspect Oriented Programming](https://github.com/gimhanul/TIL/blob/master/Spring/core/Aspect%20Oriented%20Programming/Aspect%20Oriented%20Programming.md)
    - 1-2-1. [AOP의 기본 개념](https://github.com/gimhanul/TIL/blob/master/Spring/core/Aspect%20Oriented%20Programming/AOP%EC%9D%98%20%EA%B8%B0%EB%B3%B8%20%EA%B0%9C%EB%85%90.md)
    - 1-2-2. [AspectJ](https://github.com/gimhanul/TIL/blob/master/Spring/core/Aspect%20Oriented%20Programming/AspectJ.md)
- 1-3. [Validation](https://github.com/gimhanul/TIL/blob/master/Spring/core/Validation/validation.md)
    - 1-3-1. [종류](https://github.com/gimhanul/TIL/blob/master/Spring/core/Validation/%EC%A2%85%EB%A5%98.md)
    - 1-3-2. [Spring Validation](https://github.com/gimhanul/TIL/blob/master/Spring/core/Validation/spring%EC%9D%98%20validation/spring%EC%9D%98%20validation.md)
        - 1-3-2-1. [Java Bean Validation](https://github.com/gimhanul/TIL/blob/master/Spring/core/Validation/spring%EC%9D%98%20validation/Java%20Bean%20Validation.md)
        - 1-3-2-2. [Spring validator Interface 구현](https://github.com/gimhanul/TIL/blob/master/Spring/core/Validation/spring%EC%9D%98%20validation/spring%20validator%20interface%20%EA%B5%AC%ED%98%84.md)
    - 1-3-3. [주의사항](https://github.com/gimhanul/TIL/blob/master/Spring/core/Validation/%EC%A3%BC%EC%9D%98%EC%82%AC%ED%95%AD.md)
    - 1-3-4. [실무 활용 패턴](https://github.com/gimhanul/TIL/blob/master/Spring/core/Validation/%EC%8B%A4%EB%AC%B4%ED%99%9C%EC%9A%A9%ED%8C%A8%ED%84%B4.md)
- 1-4. [Data Binding](https://github.com/gimhanul/TIL/blob/master/Spring/core/Data%20Binding/Data%20Binding.md)
    - 1-4-1. [Converter](https://github.com/gimhanul/TIL/blob/master/Spring/core/Data%20Binding/converter.md)
    - 1-4-2. [Formatter](https://github.com/gimhanul/TIL/blob/master/Spring/core/Data%20Binding/formatter.md)
- 1-5. [Resource](https://github.com/gimhanul/TIL/blob/master/Spring/core/Resource/resource.md)
    - 1-5-1. [Resource 구현체](https://github.com/gimhanul/TIL/blob/master/Spring/core/Resource/resource%20%EA%B5%AC%ED%98%84%EC%B2%B4.md)
    - 1-5-2. [Spring Resource Loader](https://github.com/gimhanul/TIL/blob/master/Spring/core/Resource/Spring%20ResourceLoader.md)
    - 1-5-3. [ResourcePatternResolver](https://github.com/gimhanul/TIL/blob/master/Spring/core/Resource/ResourcePatternResolver.md)
    - 1-5-4. [applicationContext and Resource Paths](https://github.com/gimhanul/TIL/blob/master/Spring/core/Resource/ApplicationContexts%20and%20Resource%20Paths.md)
- 1-6. [Spring Expression Language](https://github.com/gimhanul/TIL/blob/master/Spring/core/SpEL/SpEL.md)
    - 1-6-1. [SpEL의 값 평가(evaluation)](https://github.com/gimhanul/TIL/blob/master/Spring/core/SpEL/SpLE%EC%9D%98%20%EA%B0%92%20%ED%8F%89%EA%B0%80.md)
    - 1-6-2. [Bean의 Property를 설정할 때 사용하는 방식](https://github.com/gimhanul/TIL/blob/master/Spring/core/SpEL/Bean%EC%9D%98%20Property%EB%A5%BC%20%EC%84%A4%EC%A0%95%ED%95%A0%20%EB%95%8C%20%EC%82%AC%EC%9A%A9%ED%95%98%EB%8A%94%20%EB%B0%A9%EC%8B%9D.md)
- 1-7. [Null Safety](https://github.com/gimhanul/TIL/blob/master/Spring/core/Null%20Safety/Null%20Safety.md)
    - 1-7-1. [@NonNull](https://github.com/gimhanul/TIL/blob/master/Spring/core/Null%20Safety/%40NonNull.md)
    - 1-7-2. [@Nullable](https://github.com/gimhanul/TIL/blob/master/Spring/core/Null%20Safety/%40Nullable.md)

<br>

## 2. Spring Security

- 2-1. [내부구조](https://github.com/gimhanul/TIL/blob/master/Spring/Security/%EB%82%B4%EB%B6%80%EA%B5%AC%EC%A1%B0.md)
- 2-2. SecurityContextHolderStrategy
    - 2-2-1. [ThreadLocal](https://github.com/gimhanul/TIL/blob/master/Spring/Security/SecurityContextHolderStrategy/ThreadLocal.md)
    - 2-2-2. [InheritableThreadLocal](https://github.com/gimhanul/TIL/blob/master/Spring/Security/SecurityContextHolderStrategy/InheritableThreadLocal.md)
    - 2-2-3. [Global](https://github.com/gimhanul/TIL/blob/master/Spring/Security/SecurityContextHolderStrategy/Global.md)
- 2-3. [PasswordEncoder](https://github.com/gimhanul/TIL/tree/master/Spring/Security/PasswordEncoder/PasswordEncoder.md)
    - 2-3-1. [종류](https://github.com/gimhanul/TIL/blob/master/Spring/Security/PasswordEncoder/PasswordEncoder.md)
    - 2-3-2. [DelegatingPasswordEncoder](https://github.com/gimhanul/TIL/blob/master/Spring/Security/PasswordEncoder/DelegatingPasswordEncoder.md)
- 2-4. [Filter](https://github.com/gimhanul/TIL/blob/master/Spring/Security/Filter/Filter.md)
    - 2-4-1. [SecurityContextPersistenceFilter](https://github.com/gimhanul/TIL/blob/master/Spring/Security/Filter/SecurityContextPersistenceFilter.md)
    - 2-4-2. [BasicAuthenticationFilter](https://github.com/gimhanul/TIL/blob/master/Spring/Security/Filter/BasicAuthenticationFilter.md)
    - 2-4-3. [UsernamePasswordAuthenticationFilter](https://github.com/gimhanul/TIL/blob/master/Spring/Security/Filter/UsernamePasswordAuthenticationFilter.md)
    - 2-4-4. [CsrfFilter](https://github.com/gimhanul/TIL/blob/master/Spring/Security/Filter/CsrfFilter.md)
    - 2-4-5. [RememberMeAuthenticationFilter](https://github.com/gimhanul/TIL/blob/master/Spring/Security/Filter/RememberMeAuthenticationFilter.md)
    - 2-4-6. [AnonymousAuthenticationFilter](https://github.com/gimhanul/TIL/blob/master/Spring/Security/Filter/AnonymousAuthenticationFilter.md)
    - 2-4-7. [FilterSecurityInterceptor](https://github.com/gimhanul/TIL/blob/master/Spring/Security/Filter/FilterSecurityInterceptor.md)
    - 2-4-8. [ExceptionTranslationFilter](https://github.com/gimhanul/TIL/blob/master/Spring/Security/Filter/ExceptionTranslationFilter.md)
- 2-5. 부가기능
    - 2-5-1. [Spring Security Config](https://github.com/gimhanul/TIL/tree/master/Spring/Security/add-ons/Config.md)
    - 2-5-2. [UrlMatchers](https://github.com/gimhanul/TIL/tree/master/Spring/Security/add-ons/UrlMatchers.md)
    - 2-5-3. [Test](https://github.com/gimhanul/TIL/tree/master/Spring/Security/add-ons/Test.md)
    - 2-5-4. [Custom Filter](https://github.com/gimhanul/TIL/tree/master/Spring/Security/add-ons/CustomFilter.md)
- 2-6. JWT
    - 2-6-1. [session으로 인증]()
    - 2-6-2. [token으로 인증]()
    - 2-6-3. [JWT Structure]()
    - 2-6-4. [Key Rolling]()