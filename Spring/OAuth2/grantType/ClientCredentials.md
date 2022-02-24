### 3-2-4. Client Credentials Grant Type

클라이언트 자격 증명 타입.

resource owner에 대한 자격 증명을 하지 않는 유일한 방식임.

client_id, client_secret으로만 자격 증명을 진행함.

refresh token 정보는 내려주지 않음.

<br>

**동작 방식**

![](https://github.com/cheese10yun/TIL/raw/master/assets/Client%20Credentials%20Grant%20Type.png)

1. resource owner가 authorization server에 Access Token을 요청함.
    > client_id, client_secret, grant_type 파라미터를 보냄.
2. `Access Token`을 응답함. refresh token 안 보냄.
3. 받은 Access Token을 이용해서 resource server를 이용함.