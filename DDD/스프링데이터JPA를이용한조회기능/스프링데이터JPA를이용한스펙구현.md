## 5.3. 스프링 데이터 JPA를 이용한 스펙 구현

스프링 데이터 JPA 는 검색 조건을 표현하기 위한 Specification 을 제공하며, 다음과 같이 정의되어 있음.

```java
public interface Specification<T> extends Serializable {
    // not, where, and, or 메서드 생략
    
    @Nullable
    Predicate toPredicate(Root<T> root,
                          CriteriaQuery<?> query,
                          CriteriaBuilder cb);
}
```

- `T`: JPA 엔티티 타입
- `toPredicate()`: JPA 크리테리아 `Criteria` API 에서 조건을 표현하는 Predicate 생성

<br>

### 스펙 구현 예시: 스펙 구현 클래스 개별적으로 생성

- 엔티티 타입이 OrderSummary
- ordererId 프로퍼티 값이 지정한 값과 동일

```java
public class OrdererIdSpec implements Specification<OrderSummary> {
    
    private String ordererId;
    
    public OrdererIdSpec(String ordererId) {
        this.ordererId = ordererId;
    }
    
    @Override 
    public Predicate toPredicate(Root<OrderSummary> root,
                                 CriteriaQuery<?> query,
                                 CriteriaBuilder cb) {
        return cb.equal(root.get(OrderSummary_.ordererId), ordererId);
    }
}
```

<details>
<summary>OrderSummary_ : JPA 정적 메타 모델</summary>

`OrderSummary_` 클래스는 JPA 정적 메타 모델을 정의한 코드로, 다음과 같이 구현함.

```java
@StaticMetamodel(OrderSummary.class)
public class OrderSummary_ {
    public static volatile SingularAtttribute<OrderSummary, String> number;
    public static volatile SingularAtttribute<OrderSummary, Long> version;
    public static volatile SingularAtttribute<OrderSummary, String> ordererId;
    public static volatile SingularAtttribute<OrderSummary, String> ordererName;
    ...
}
```

- 정적 메타모델은 `@StaticMetamodel` 애너테이션을 이용해서 관련 모델을 지정함.
- 메타 모델 클래스는 모델 클래스의 이름 뒤에 `_`을 붙인 이름을 가짐.
- 정적 메타 모델 클래스는 대상 모델의 각 프로퍼티와 동일한 이름을 갖는 정적 필드를 정의함.
- 이 정적 필드는 프로퍼티에 대한 메타 모델로서 프로퍼티 타입에 따라 Singular Attribute, ListAttribute 등의 타입을 이용해서 메타 모델을 정의함.

다음과 같이 문자열로 프로퍼티를 지정해도 동작은 함.

```java
cb.equal(root.<String>get("ordererId"), ordererId)
```

하지만 문자열은 오타 가능성이 있고, 실행하기 전까지는 오타가 있다는 것을 놓치기 쉬움. 게다가 IDE 의 자동완성 기능을 사용할 수 없어 입력할 코드도 많아짐.

따라서 정적 메타 모델 클래스를 사용하는 것이 코드 안정성이나 생산성 측면에서 유리함.

정적 메타 모델 클래스를 직접 작성할 수 있지만, 하이버네이트 같은 JPA 프로바이더는 정적 메타 모델을 생성하는 도구를 제공하고 있으므로 이들 도구를 사용하면 편리함.

</details>

이는 OrdererSummary 에 대한 검색 조건을 표현함.

`toPredicate()` 메서드는 ordererId 프로퍼티 값이 전달받은 ordererId 와 동일한지 비교하는 Predicate 를 생성함.

<br>

### 스펙 구현 예시: 별도 클래스에 스펙 생성 기능 모음

OrderSummary 와 관련된 스펙 생성 기능을 한 클래스에 모을 수 있음.

```java
public class OrderSummarySpecs {
    
    public static Specification<OrderSummary> ordererId(String ordererId) {
        return (Root<OrderSummary> root, CriteriaQuery<?> query,
                CriteriaBuilder cb) ->
                cb.equal(root.<String>get("ordererId"), ordererId);
    }

    public static Specification<OrderSummary> orderDateBetween(
            LocalDateTime from, LocalDateTime to
    ) {
        return (Root<OrderSummary> root, CriteriaQuery<?> query,
                CriteriaBuilder cb) ->
                cb.between(root.get(OrderSummary_.orderDate), from, to);
    } 
}
```

스펙 생성이 필요한 코드는 스펙 생성 기능을 제공하는 클래스를 이용해서 더 간결하게 스펙을 생성할 수 있음.

```java
Specification<OrderSummary> betweenSpec = 
    OrderSummarySpecs.orderDateBetween(from, to);
```