## 5-1. Spring Boot

**스프링을 기반**으로 실무 환경에 사용 가능한 수준의 **독립실행형 애플리케이션**을 복잡한 고민 없이 빠르게 작성할 수 있게 도와주는 여러가지 도구의 모음.

> 스프링 부트와 스프링은 다름.

<br>

### 핵심 목표

- 매우 빠르고 광범위한 영역의 스프링 개발 경험 제공
- 강한 주장을 가지고 즉시 적용 가능한 기술 조합을 제공하면서, 필요에 따라 원하는 방식으로 손쉽게 변형 가능
- 프로젝트에서 필요로 하는 다양한 비기능적인 기술(내장형 서버, 보안, 메트릭, 상태 체크, 외부 설정 방식 등) 제공
- 코드 생성이나 XML 설정을 필요로 하지 않음

<br>

### 역사

- 2012년 스프링 프레임워크 프로젝트에 이슈로 등록된 <Containerless 웹 개발 아키텍처의 지원> 요청에서 논의와 개발 시작
- 2013년 0.5.0.M1 공개
- 2014년 1.0 GA 공개
- 2018년 2.0 GA 공개
- 2022년 2.7.5 공개

<br>

### Containerless

> Serverless 와 비슷함.

#### Web Component
- 기능을 제공함.
- web client 와 request, response 를 주고받으며 상호작용함.
- dynamic content 를 만듦.

#### Web Container
- life cycle 을 관리함. 
- 여러 web component 를 관리함. 
- client 가 보낸 요청을 적절한 web component 에 전달함.

#### Java
- Servlet = web component
- Servlet Container = web container(ex: tomcat)

#### Spring framework
- Spring Container <-> servlet container
- Bean <-> servlet

> Servlet Container 를 대체하지 않음. 뒤에 존재함.
> java 의 표준 웹 기능을 사용하려면 무조건 Servlet Container 가 존재해야 하기 떄문임.
> 따라서 Spring framework 를 사용하려면 Servlet Container 를 위한 엄청난 설정을 해야 했음.

#### Containerless

<img width="538" alt="image" src="https://user-images.githubusercontent.com/80656733/215734411-a4b31665-62ab-476f-bd2b-5465e176179e.png">

Spring Boot 를 이용하면 Servlet Container 를 따로 설정할 필요가 없음.

<br>

### Opinionated

#### Spring framework 설계 철학
- 극단적인 유연함 추구
- 다양한 관점을 수용
- Not Opinionated
- 수많은 선택지를 다 포용

#### Spring Boot 설계 철학
- Opinionated - 자기 주장이 강한, 자기 의견을 고집하는, 독선적인
- 일단 정해주는 대로 빠르게 개발하고 고민은 나중에
- 스프링을 잘 활용하는 뛰어난 방법을 제공

#### Spring Boot 가 결정해 주는 것
- {업계에서 검증된 스프링 생태계 프로젝트, 표준 자바 기술, 오픈소스 기술}의 종류와 의존 관계, 사용 버전
- 각 기술을 스프링에서 적용하는 방식(DI 구성)과 디폴트 설정값 제공

#### 유연한 확장
- 스프링 부트에 내장된 디폴트 구성을 customizing 하는 매우 자연스럽고 유연한 방법 제공
- 스프링 부트가 스프링을 사용하는 방식을 이해한다면 언제라도 스프링 부트를 제거하고 원하는 방식으로 재구성 가능
- 스프링 부트처럼 기술과 구성을 간편하게 제공하는 나만의 모듈 작성