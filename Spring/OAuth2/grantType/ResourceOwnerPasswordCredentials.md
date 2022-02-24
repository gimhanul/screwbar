### 3-2-3. Resource Owner Password Credentials Grant Type

리소스 소유자 암호 자격 증명 타입.

resource owner의 계정 정보를 기반으로 인증 처리를 함.

ID, PW 기반으로 진행하는 만큼 직관적인 인증 방법임.

refresh token 정보는 내려줄지 안내려줄지 정할 수 있음.

<br>

**동작 방식**

![](https://github.com/cheese10yun/TIL/raw/master/assets/Resource%20Owner%20Password%20Credentials%20Grant.png)

1. resource owner가 client에게 authentication을 요청함.
2. client가 authorization에게 resource owner의 계정 정보를 기반으로 `Access Token`을 요청함.
    > client_id, client_secret, grant_type, username, password 파라미터를 보냄.
3. Access Token을 응답함. refresh token은 Optional.
4. 받은 Access Token을 사용해서 resource server를 이용할 수 있음.