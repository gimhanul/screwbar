## 2-1. CREATE

CREATE는 테이블을 생성하는 명령어임.

```sql
CREATE TABLE <table name> (
    <column name> <data type> [ NOT NULL | UNIQUE | DEFAULT | CHECK ],
    ...
    primary key(<column name>)
);
```

> `primary key`를 column 뒤에 적어서 지정할 수도 있음.

과 같은 형태로 불러올 수 있음.

<br>

<br>

**제약 조건**

- 제약조건을 걸 column 뒤에 그냥 써서 추가함.

|제약 조건|설명|
|--|--|
|NOT NULL|NULL값 안허용|
|UNIQUE|유일한 값|
|DEFAULT|기본값 설정|
|CHECK|값에 대한 조건 부여|

<br>

<br>

**Foreign Key**

- 다음과 같이 외래키 지정할 수 있음.

```sql
FOREIGN KEY <column name> REFERENCES <table name(column)>
   ON DELETE [ CASCADE | SET NULL ]
```

<br>

<br>

**ON DELETE**

- 부모 테이블에서 외래키가 삭제되었을 때 할 행동을 결정함.

|option|설명|
|---|---|
|CASCADE|나두 삭제|
|SET NULL|NULL 값으로 변경|
|RESTRICT|아무 일도 일어나지 않음|

> 아무것도 명시하지 않았을 때 RESTRICT 임.