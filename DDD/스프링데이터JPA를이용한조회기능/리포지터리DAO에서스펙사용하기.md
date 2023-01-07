## 5.4. 리포지터리/DAO에서 스펙 사용하기

스펙을 충족하는 엔티티를 검색하고 싶다면 `findAll` 메서드를 사용하면 됨.

```java
public interface OrderSummaryDao extends Repository<OrderSummary, String> {
    List<OrderSummary> findAll(Specification<OrderSummary> spec);
}
```

`findAll` 메서드는 OrderSummary 에 대한 검색 조건을 표현하는 스펙 인터페이스를 가짐.