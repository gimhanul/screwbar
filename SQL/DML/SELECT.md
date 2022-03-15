## 3-1. SELECT

SELECT는 데이터를 불러오는 명령어임.

```sql
SELECT <attribute> FROM <tableName>
```

과 같은 형태로 불러올 수 있음.

<br>

<br>

**attribute**

- 속성을 불러올 때는 불러올 column명을 사용함.

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

```sql
SELECT * FROM <tableName> WHERE <condition>
```

> 문자열을 비교할 때는 `==` 을 사용하지 않고 `like`를 사용함.