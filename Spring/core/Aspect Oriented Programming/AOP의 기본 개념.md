### 1-2-1. AOP의 기본 개념
<br>

**Aspect**

여러 클래스나 기능에 걸쳐서 있는 관심사. 그리고 그것을 모듈화 함.

AOP 중에 가장 많이 활용되는 부분은 @Transactional (트랜잭션 관리) 기능.

<br>

**Advice**

조언. AOP에서 실제로 적용하는 기능(로깅, 트랜잭션, 인증 등)을 뜻함. 

<br>

**Join point**

모듈화된 특정 기능이 실행될 수 있는 연결 포인트.

<br>

**Point cut**

Join point 중에서 해당 Aspect를 적용할 대상을 뽑은 조건식.

<br>

**Target Object**

Advice가 적용될 대상 object.

<br>

**AOP Proxy**

Target Object에 Aspect를 적용하는 경우 Target Object에 Advice를 덧붙이기 위해 하는 작업.

주로 CGLIB(Code Generation Library, 실행 중에 실시간으로 코드를 생성하는 라이브러리) 프록시를 사용하여 프록싱 작업을 함.

<br>

**Weabing**

Advice를 비즈니스 로직 코드에 삽입하는 것.