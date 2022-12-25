## 2.3. DIP

### 가격 할인 계산 예시

가격 할인 계산을 하려면

1. 고객 정보 구하기
2. 구한 고객 정보와 주문 정보를 이용해 룰을 실행해야 함.

![](https://user-images.githubusercontent.com/42582516/149946529-0ed784a4-c16e-4f55-8fcb-5f51ab5b8a17.png)

이때, 고수준 모듈 `CalculateDiscountService` 은 하위 기능을 구현한 저수준 모듈을 사용해야 함.

그런데 고수준 모듈이 저수준 모듈을 사용하면 '구현 변경', '테스트'가 어렵다는 문제가 발생함.

<br>

### DIP

Dependency Inversion Principle, 의존 역전 원칙.

**추상화한 인터페이스**를 사용해 **저수준 모듈이 고수준 모듈에 의존**하도록 바꿈.

`CalculateDiscountService` 입장에서 봤을 때 룰 적용을 뭐로 구현했는지는 중요하지 않음.

이를 추상화한 인터페이스는 다음과 같음.

```java
public interface RuleDiscounter {
    Money applyRules(Customer customer, List<OrderLine> orderLines);
}
```

`CalculateDiscountService` 가 `RuleDiscounter` 를 이용하도록 바꿈.

```java
public class CalculateDiscountService {
    
    private RuleDiscounter ruleDiscounter;
    
    public CalculateDiscountService(RuleDiscounter ruleDiscounter) {
        this.ruleDiscounter = ruleDiscounter;
    }
    
    public Money calculateDiscount(List<OrderLine> orderLines, String customerId) {
        Customer customer = findCustomer(customerId);
        return ruleDiscounter.applyRules(customer, orderLines);
    }
}
```

> `CalculateDiscountService` 에는 `Drools` 라이브러리에 의존하는 코드가 없음.

룰 적용을 구현한 클래스는 `RuleDiscounter` 인터페이스를 상속받아 구현함.

```java
public class DroolsRuleDiscounter implements RuleDiscounter {
    
    private KieContainer kContainer;
    
    public DroolsRuleDiscounter() {
        KieService ks = KieServices.Factory.get();
        kContainer = ks.getKieClasspathContainer();
    }
    
    @Override
    public Money applyRules(Customer customer, List<OrderLine> orderLines) {
        KieSession kSession = kContainer.newKieSession("discountSession");
        
        try {
            // 코드 생략
            kSession.fireAllRules();
        } finally {
            kSession.dispose();
        }
        
        return money.toImmutableMoney();
    }
}
```

그럼 다음과 같이 저수준 모듈이 고수준 모듈에 의존하게 됨.

![](https://user-images.githubusercontent.com/42582516/150043420-196ea35c-0492-4033-9275-2e9c9a793ca8.png)

<br>

### 구현 기술 교체 문제 해결

실제 사용할 저수준 구현 객체는 의존 주입을 이용해 전달 받을 수 있음.

```java
// 사용할 저수준 객체 생성
RuleDiscounter ruleDiscounter = new DroolsRuleDiscounter();

// 생성자 방식으로 주입
CalculateDiscountService disService = new CalculateDiscountService(ruleDiscounter);
```

구현 기술을 변경하더라도 `CalculateDiscountService` 를 수정할 필요 없이 저수준 구현 객체를 생성하는 코드만 변경하면 됨.

```java
// 사용할 저수준 객체 생성
RuleDiscounter ruleDiscounter = new SimpleRuleDiscounter();

// 생성자 방식으로 주입
CalculateDiscountService disService = new CalculateDiscountService(ruleDiscounter);
```

<br>

### 테스트 불가능 문제 해결 

실제 구현이 없어도 Mock 프레임워크를 사용해 스텁이나 모의 객체와 같은 **테스트 목적의 대역**을 사용하여 거의 모든 상황을 테스트 할 수 있음.

```java
public class CalculateDiscountServiceTest {
    
    @Test
    public void noCustomer_thenExceptionShouldBeThrown() {
        // given 
        CustomerRepository stubRepo = mock(CustomerRepository.class);
        when(stubRepo.findById("noCustId")).thenReturn(null);
        
        RuleDisconter stubRule = (cust, lines) -> null;
        
        CalculateDiscountService calDisSvc = new CalculateDiscountService(stubRepo, stubRule);
        
        // when and then
        assertThrows(NoCustomerException.class, () -> calDisSvc.calculateDiscount(someLines, "noCustId"));
    }
}
```

<br>

### DIP 주의사항

DIP 를 잘못 생각하면 단순히 인터페이스와 구현 클래스를 분리하는 정도로 받아들일 수 있음.

이때, DIP 의 핵심은 고수준 모듈이 저수준 모듈에 의존하지 않도록 하기 위함인데, 저수준 모듈에서 인터페이스를 추출하는 경우가 있음.

![](https://user-images.githubusercontent.com/42582516/150043420-196ea35c-0492-4033-9275-2e9c9a793ca8.png)

> DIP를 적용할 때 하위 기능을 추상화한 인터페이스는 **고수준 모듈 관점**에서 도출하며, 이는 고수준 모듈에 위치함.

<br>

### DIP 와 아키텍처

DIP 를 적용하면 다음과 같이 인프라스트럭처 영역이 응용 영역과 도메인 영역에 의존하는 구조가 됨.

![](https://user-images.githubusercontent.com/42582516/150043561-7309f180-6cd2-4bda-a1e4-aa7b87683c72.png)

이떄, 응용 영역과 도메인 영역에 영향을 최소화하면서 구현체를 변경하거나 추가할 수 있음.