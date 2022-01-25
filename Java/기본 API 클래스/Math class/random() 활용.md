### 9-6-1. random() 활용

Math.random()은 0.0과 1.0 사이의 double 타입의 값을 return함.

0.0은 포함되고 1.0은 포함되지 않음.

이때, 0부터 9사이의 값을 얻기 위해서는

1. 메소드를 돌려서 나온 값에 10을 곱함.
2. 값을 int 타입으로 강제 타입 변환함.

```java
int num = (int) (Math.random() * 10);
```

만약 범위가 1 ≤ 랜덤값 < n 이라면,

```java
int num = (int) (Math.random() * n) + 1;
```