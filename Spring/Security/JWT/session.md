### 2-6-1. session으로 인증

![image](https://user-images.githubusercontent.com/80656733/155308702-97ff3f9b-5ac1-46ce-a889-1056dc41b22a.png)

session은 위와 같이 동작함.

<br>

**장점**

- JSESSIONID는 유의미한 값이 아니라, server에서 session(user) 정보를 찾는 Key로만 활용함.
- 따라서 탈취되었다고 해서 개인정보가 탈취된 건 아님.

<br>

**단점**

- 세션하이제킹 공격을 당할 수 있기 때문에 개인정보에 절대적으로 안전한 것은 아님.
    > 세션하이제킹 공격 : JSESESSIONID를 훔쳐서 마치 그 user인 것마냥 행동하는 것을 말함.
- server에 session(user) 정보를 저장할 공간이 필요함.
- 분산 server에서는 session을 공유하는 데 어려움이 있음.
    > session server를 따로 두거나 server들의 session을 공유하는 방식으로 해결할 수 있지만 매우 어려움.