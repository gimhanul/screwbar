### 3-2-2. Implicit Grant Type

암시적 승인 타입.

[Authorization Code Grant Type]() 과 거의 동일함.

차이점은 Authorization Code를 사용하지 않는 것이며, 이를 묵시적인 승인을 받았다고 함.

권한 서버가 Authorization Code를 생략하고 바로 Access Token을 응답함.

해당 Access Token이 유효한지 권한 서버가 한 번 더 검증함.

refresh token은 넘겨주지 않음.

<br>

**동작 방식**

![](https://github.com/cheese10yun/TIL/raw/master/assets/Implicit%20Grant.png)

1. client가 authorization server에 `권한 부여 코드`를 요청함.
    > client_id, redirect_url, response_type=token 파라미터로 요청함.
2. 파라미터 내용을 검증한 뒤 바로 `Access Token`을 응답함.
3. client가 authorization server에 Access Token 을 검증해 달라고 보냄.
4. 검증 내용을 돌려줌.
5. client는 검증된 Access Token을 가지고 resource server를 이용할 수 있음.