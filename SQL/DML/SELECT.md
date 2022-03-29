## 3-1. SELECT

SELECT는 데이터를 불러오는 명령어임.

```sql
SELECT <attribute> FROM <tableName>
```

과 같은 형태로 불러올 수 있음.

<br>

<br>

**attribute**

- 속성을 불러올 때는 불러올 column명을 사용함. 쓴 순서대로 나옮.

|개수|ex|
|--|--|
|한 개|`SELECT <특정 attribute> FROM <tableName>`|
|여러 개|`SELECT <attribute1>, <attribute2>, ••• FROM <tableName>`|
|전부|`SELECT * FROM <tableName>`|

<br>

- `as` 를 사용해서 특정 column을 불러올 때 다른 이름으로 표시할 수 있음.

```sql
SELECT name as 이름, price as 가격 FROM <tableName>
```

> 생략 가능함.

<br>

<br>

**WHERE**

- WHERE을 뒤에 붙여 SELECT 조건을 달아줄 수 있음.
- `AND`, `OR` 등 복합 연산자를 통해 여러 개의 조건을 달 수 있음.

```sql
SELECT * FROM <tableName> WHERE <condition>
```

|술어|연산자|
|---|---|
|같다|=|
|같지 않다|<>|
|범위 지정|속성 between 어쩌구 and 저쩌구|
|집합|in (집합)|
|패턴|like 어쩌구|
|널|is null, is not null|


<br>

**문자열 관련한 꿀팁**

> 문자열을 비교할 때는 `==` 을 사용하지 않고 `like`를 사용함.

> like 에서 `%` 쓰면 그 위치에 여러 글자인 뭐가 와도 괜찮다

|형식|설명|
|---|---|
|%축구|축구로 끝나는 단어|
|축구%|축구로 시작하는 단어|
|%축구%|축구를 포함하는 단어|

> `_` 쓰면 한 글자 뭐가 와도 괜찮다는 뜻

<br>

<br>


**distinct**

중복제거

```sql
select distinct publisher
from book
```

<br>

<br>

**ORDER BY**

```sql
ORDER BY 기준(속성)
```

속성을 기준으로 정렬함.

- 내림차순: `desc` (null은 최대치 인식)
- 오름차순: `asc` (default)

> 문자 정렬 기준은 숫자 -> 영문자 -> 한글

> 기준 여러 개 쓰고 싶으면 그냥 여러 개 쓰기

<br>

<br>

**집계 함수**

|쓰는거|설명|
|---|---|
|sum(속성)|속성의 총합|
|avg(속성)|속성의 평균|
|count(속성)|속성의 개수|
|max(속성)|속성 값들 중 최대값|
|min(속성)|속성 값들 중 최소값|

> 집계함수에서도 다음과 같이 중복제거가 가능함. `sum(distinct price)`

<br>

<br>


**GROUP BY**

중복제거 아니라 그냥 그룹 지어준 거임.

`having`으로 group by에 대해 조건을 걸 수 있음.

<br>

<br>

**JOIN**

두 테이블을 합침.

조건을 주지 않고 select하면

관계대수의 카티션 프로덕트 연산이 됨.

> 테이블 두 개를 합칠 수 있는 모든 경우의 수가 다 나타나는 연산.

조건은 똑같이 where로 줌.