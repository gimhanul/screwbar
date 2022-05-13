## 2-2. ALERT

테이블을 수정할 수 있음.

<br>

**ADD**

- 열을 추가할 수 있음.

```sql
ALTER TABLE <table name> ADD <name> <type>;
```

<br>

**MODIFY**

- 타입을 변경할 수 있음.

```sql
ALTER TABLE <table name> MODIFY <column name> <type>;
```

<br>

**DROP**

- 콜럼을 지울 수 있음.

```sql
ALTER TABLE <table name> DROP COLUMN <column name>;
```

<br>

**pk 변경**

- 다음과 같은 순서로 pk를 변경할 수 있음.

1. 다음과 같이 제약 조건을 제거할 수 있음.


```sql
ALTER TABLE <table name> DROP CONSTRAINT <constraint name>;
```

<br>

2. 다음과 같이 제약 조건을 추가할 수 있음.

```sql
ALTER TABLE <table name>
    ADD CONSTRAINT <constraint name> <constraint>;
```
> `ALTER TABLE table ADD CONSTRAINT table_pk PRIMARY KEY(table_id);` 이런 느낌