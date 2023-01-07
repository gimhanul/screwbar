## 5.10. 하이버네이트 `@Subselect` 사용

`@Subselect` 는 쿼리 결과를 `@Entity` 매핑하는 기능임.

```java
@Entity
@Immutable
@Subselect("""
    SELECT o.order_number as number,
        o.version, o.orderer_id, o.orderer_name,
        o.total_amounts, o.receiver_name, o.state, o.order_date,
        p.product_id, p.name as product_name
    FROM purchase_order o
        INNER JOIN order_line ol
            ON o.order_number = ol.order_number
        CROSS JOIN product p
    WHERE ol.line_idx = 0
        AND ol.product_id = p.product_id
""")
@Synchronize({"purchase_order", "order_line", "product"})
public class OrderSummary {

    @Id
    private String number;

    private long version;

    @Column(name = "orderer_id")
    private String ordererId;

    @Column(name = "orderer_name")
    private String ordererName;
    
    ...

    protected OrderSummary() {
    }
}
```
`@Immutable`, `@Subselect`, `@Synchronize` 는 하이버네이트 전용 애너테이션으로, 이 태그를 사용하면 테이블이 아닌 쿼리 결과를 @Entity 로 매핑할 수 있음.

<br>

### `@Subselect`

- `@Subselect` 는 **조회 쿼리를 값으로 가짐**.
- 하이버네이트는 이 select 쿼리의 결과를 매핑할 테이블처럼 사용함.
- 데이터베이스의 뷰처럼, `@Subselect` 를 사용하면 쿼리 실행 결과를 매핑할 테이블처럼 사용함.

<br>

### `@Immutable`

1. 뷰를 수정할 수 없듯이, @Subselect 로 조회한 @Entity 역시 수정할 수 없음.
2. 실수로 매핑 필드를 수정하면 하이버네이트는 변경 내역을 반영하는 update 쿼리를 실행할 것임.
3. 그런데 매핑한 테이블이 없으므로 에러가 발생함.

→ 이런 문제를 방지하기 위해 `@Immutable` 을 사용함.
이를 사용하면, **해당 엔티티의 매핑 필드/프로퍼티가 변경돼도 DB 에 반영하지 않고 무시**함.

<br>

### `@Synchronize`

```java
// purchase_order 테이블에서 조회
Order order = orderRepository.findById(orderNumber);
order.changeShippingINfo(newInfo) // 상태 변경

// 변경 내역이 DB 에 반영되지 않았는데 purchase_order 테이블에서 조회
List<OrderSummary> summaries = orderSummaryRepository.findByOrdererId(userId);
```

위 코드는 Order 의 상태를 변경한 뒤에 OrderSummary 를 조회하고 있음. 즉, OrderSummary 에는 최신 값이 아닌 이전 값이 담김.

이런 문제를 해소하기 위한 용도로 `@Synchronize` 임.

- `@Synchronize` 는 해당 엔티티와 관련된 테이블 목록을 명시함.
- 하이버네이트는 엔티티를 로딩하기 전에 지정한 테이블과 관련된 변경이 발생하면 flush 를 먼저 함.
- OrderSummary 의 `@Synchronize` 는 'purchase_order' 테이블을 지정하고 있으므로, OrderSummary 를 로딩하기 전에 purchase_order 테이블에 변경이 발생하면 관련 내역을 먼저 flush 함.
- 따라서 OrderSummary 를 로딩하는 시점에서는 변경 내역이 반영됨.

<br>

### `@Subselect`

`@Subselect` 를 사용해도 일반 `@Entity` 와 같기 때문에, `EntityManager#find()`, JPQL, Criteria 를 사용해서 조회할 수 있고, 스펙도 사용할 수 있음.

단, Subselect 는 이름처럼 **지정한 쿼리를 from 절의 서브쿼리로 실행**함.

```sql
SELECT osm.number as number1_0_, ...
FROM (
    SELECT o.order_number as number, ...
    # 지정한 쿼리
)
WHERE osm.orderer_id=?
ORDER BY osm.number DESC
```

서브쿼리를 사용하고 싶지 않다면 네이티브 SQL 쿼리를 사용하거나 마이바티스와 같은 별도 Mapper 를 사용해서 조회 기능을 구현해야 함.