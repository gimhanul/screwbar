### 3-2-1. Authorization Code Grant Type

권한 부여 코드 승인 타입.

social login에 사용되는 인증 방식임.

권한 서버의 code를 내려주며 해당 값으로 다시 검증을 진행함.

네 가지 인증 방식 중 가장 복잡함.

<br>

**동작 방식**

![](https://github.com/cheese10yun/TIL/raw/master/assets/oauth2-doe-grant-type_gnojt19me.png)

1. client가 authorization server에 `권한 부여 코드`를 요청함.
    > client_id, redirect_url, response_type=code 파라미터로 요청함.
2. 파라미터를 검증하고 authorization server에서 권한 부여 코드를 응답함.
3. client가 코드를 가지고 authorization server에 `Access Token`으로 교환 요청을 함.
    > client_id, client_secret, redirect_url, grant_type=authorization_code 파라미터로 요청함.
4. 파라미터를 검증하고 Access Token을 응답함.
5. 위 Access Token을 사용하여 resource server를 이용할 수 있음.