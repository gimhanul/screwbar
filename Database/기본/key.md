## 2-2. Key

> relation 에서 **특정 tuple 을 식별**할 때 사용하는 attribute. 혹은 attribute 의 집합.

###  Super Key

tuple 을 unique 하게 식별할 수 있는 값.
tuple 을 식별할 수 없는 attribute 도 포함되어 있음.

```
(주민번호, 이름, 핸드폰번호)
```

### Candidate Key

tuple 을 unique 하게 식별할 수 있는 attribute 의 **최소** 집합.

### Primary Key (PK)

**Candidate Key 중 하나를 선정하여 대표**로 삼는 key.

- unique 해야 함.
- Not NULL
- 변동돼서는 안 됨.
- 최대한 적은 수의 attribute 를 가짐.

### Alternate Key

PK로 선정이 안 된 후보키를 말함.

### Foreign Key

**다른 relation 의 PK를 참조함.**

- 관계를 표현함.
- 데이터의 일관성을 유지함.
- domain 이 같아야 함.
- NULL, 중복값이 허용됨.
- 자기가 자신의 key 를 참조할 수 있음.
- PK의 일부가 될 수 있음.

### Surrogate Key

PK가 보안을 필요로 해서 가상의 속성을 만들어 PK로 삼은 것.

- 의미 없음.
