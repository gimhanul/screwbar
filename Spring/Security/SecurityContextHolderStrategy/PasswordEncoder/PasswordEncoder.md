## 2-3. PasswordEncoder

password를 관리할 때는 다음 두 가지를 만족해야 함.

1. 회원가입 할 때 입력받은 password를 암호화해서 저장해야함.
2. 로그인 할 때 입력 받은 password와 저장되어 있는 password를 비교할 수 있어야함.

<br>

따라서, 보통 다음과 같은 방식으로 password를 관리함.

1. 회원가입할 때 password를 암호화해서 저장함.
2. 로그인 할 때 password가 들어오면, 같은 방식으로 암호화함.
3. 저장된 password를 불러와서 로그인 할 때 받은 password의 암호화된 값과 비교함.
4. 동일하면 같은 암호로 판단함.