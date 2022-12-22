### 2-1. Relation

행과 열로 구성된 **table**을 말함.

| ---    | attribute1  | attribute2  | attribute3  |
|--------|-------------|-------------|-------------|
| tuple1 | instance1-1 | instance1-2 | instance1-3 |
| tuple2 | instance2-1 | instance2-2 | instance2-3 |
| tuple3 | instance3-1 | instance3-2 | instance3-3 |

- **attribute**

**속성 또는 열**. 통틀어 **스키마**라고 함.

> 스키마에는 relation 에 어떤 정보가 담길지 정의함.

attribute 의 개수는 **차수**라고 함.


- **tuple**

**행**. tuple 의 개수를 **cardinality**라고 함.


- **instance**

**저장된 데이터**들을 의미함.


- **domain**

**속성이 가질 수 있는 값**의 집합임.
INT, CHAR 등을 의미함.


### 특징

- attribute 는 단일값임.
- attribute 는 서로 다른 이름을 가져야 함.
- 한 attribute 는 모두 같은 domain 을 가져야 함.
- relation 내 중복 tuple 은 허용하지 않음.
- tuple 의 순서는 상관 없음.
