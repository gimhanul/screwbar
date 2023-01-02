## 4.1. JPA 를 이용한 리포지터리 구현

자바의 ORM 표준인 JPA 를 이용해서 리포지터리와 애그리거트를 구현하는 방법

### 모듈 위치

리포지터리 인터페이스는 애그리거트와 같이 도메인 영역에 속하고, 리포지터리를 구현한 클래스는 인프라스트럭처 영역에 속함.

![](https://3553248446-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-M5HOStxvx-Jr0fqZhyW%2F-MB9IKoitGfg2176-vEP%2F-MB9I_GGf4JfECn6hV54%2F4.1.png?alt=media&token=745be26e-e110-4a79-aa5f-76094d984f53)

가능하면 리포지터리 구현 클래스를 인프라스트럭처 영역에 위치시켜서 인프라스트럭처에 대한 의존을 낮춰야 함.

<br>

### 리포지터리 기본 기능 구현

리포지터리가 제공하는 기본 기능은 다음 두 가지임.

- ID 로 애그리거트 조회하기
- 애그리거트 저장하기

두 메서드를 위한 리포지터리 인터페이스는 다음과 같은 형식을 가짐.

```java
public interface OrderRepository {
    Order findById(OrderNo no);
    void save(Order order);
}
```

인터페이스는 애그리거트 루트를 기준으로 작성함.

애그리거트를 조회하는 기능의 이름을 지을 때 널리 사용되는 규칙은 `findBy프로퍼티이름(프로퍼티 값)` 형식임.

이 인터페이스를 구현한 클래스는 JPA 의 `EntityManager` 를 이용해서 기능을 구현함.

```java
@Repository
public class JpaOrderRepository implements OrderRepository {
    
    @PersistenceContext
    private EntityManager entityManager;
    
    @Override 
    public Order findById(OrderNo id) {
        return entityManager.find(Order.class, id);
    }
    
    @Override 
    public void save(Order order) {
        entityManager.persist(order);
    }
}
```

애그리거트를 수정한 결과를 저장소에 반영하는 메서드를 추가할 필요는 없음.

 JPA 를 사용하면 트랜잭션 범위에서 변경한 데이터를 자동으로 DB 에 반영하기 때문임.