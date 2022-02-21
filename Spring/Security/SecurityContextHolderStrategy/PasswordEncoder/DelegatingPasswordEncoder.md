### 2-3-2. DelegatingPasswordEncoder

spring security는 DelegatingPasswordEncoder라는 `대표 PasswordEncoder`를 따로 만들어서 사용함.

- 모든 PasswordEncoder를 선택할 수 있음.
- 기본 Encoder는 Bcrypt임.