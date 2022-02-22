### 2-4-3. UsernamePasswordAuthenticationFilter

Form 데이터로 username, password 기반의 인증을 담당하는 Filter임.

<br>

UsernamePasswordAuthenticationFilter는 다음과 같은 순서로 동작함.

1. ProviderManager(AuthenticationManager)
    - 인증 정보 제공 관리자

2. AbstractUserDetailsAuthenticationProvider
    - 인증 정보 제공
    - 계정의 상태나 패스워드 일치 여부 등을 파악

3. DaoAuthenticationProvider
    - 유저 정보 제공

4. UserDetailsService
    - 유저 정보 제공하는 Service