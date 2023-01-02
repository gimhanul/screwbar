## 4.2. 스프링 데이터 JPA를 이용한 리포지터리 구현

스프링과 JPA 를 함께 적용할 때는 스프링 데이터 JPA 를 사용함.

스프링 데이터 JPA 는 지정한 규칙에 맞게 리포지터리 인터페이스를 정의하면 리포지터리를 구현한 객체를 알아서 만들어 빈으로 등록해줌.

리포지터리 인터페이스를 직접 구현하지 않아도 되기 떄문에 개발자는 리포지터리를 쉽게 정의할 수 있음.

### 생성 규칙

다음 규칙에 따라 작성한 인터페이스를 찾아서 인터페이스를 구현한 스프링 빈 객체를 자동으로 등록함.

- `org.springframework.data.repository.Repository<T, ID>` 인터페이스 상속
- T 는 엔티티 타입을 지정하고 ID 는 식별자 타입을 지정

### 주입 

리포지터리가 필요하면 주입 받아 사용하면 됨.

```java
@Service
public class CancelOrderService {
    
    private OrderRepository orderRepository;
    
    public CancelOrderService(OrderRepository orderRepository, ...) {
        this.orderRepository = orderRepository;
        ...
    }
}
```

### 사용

이를 사용하려면 지정한 규칙에 맞게 메서드를 작성해야 함.

**저장**

- `Order save(Order order)`
- `void save(Order order)`

**식별자 이용 조회**

- `Order findById(OrderNo id)`
- `Optional<Order> findById(OrderNo id)`


**특정프로퍼티 이용 조회**

- `findBy프로퍼티이름(프로퍼티 값)`
- `List<Order> findByOrderer(Orderer orderer)`
- `List<Order> findByOrdererMemberId(MemberId memberId)`
  > 중첩 프로퍼티, 이 메서드는 Orderer 객체의 memberId 프로퍼티를 이용해 조회함.

**삭제**

- `void delete(Order order)`
- `void deleteById(OrderNo id)`