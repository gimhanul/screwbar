### 2-6-2. token으로 인증

session의 단점을 해결하기 위해 token을 사용함.

![image](https://user-images.githubusercontent.com/80656733/155311411-9b718f86-c93b-43df-9a94-567d10359ae5.png)

user가 login을 하면 server에서는 token을 생성한 뒤 저장하지 않고(stateless) token 값을 내려줌.

이 token 값은 `user를 설명할 수 있는 data를 포함`하는 유의미한 값임. (ex username)

따라서 token 과 함께 들어온 requeest를 보내면, token을 검증하고 response를 내려줌.

<br>

**장점**

- session 관리를 할 필요가 없어 별도의 저장소가 필요하지 않음.
- 분산 서버와 클러스터 환경에서 확장성이 좋음.

<br>

**단점**

- 한 번 제공된 token은 회수가 어려움.
    > 그래서 token의 유효기한을 짧게함.
- token에는 user의 정보가 있기 때문에 상대적으로 안정성이 우려됨.
    > 따라서 민감정보를 token에 포함시키면 안 됨. (ex password)