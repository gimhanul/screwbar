### 2-6-3. JWT Structure

**JWT** 는 Json Web Token의 줄임말로, token의 한 방식임.

<br>

JWT의 구조는 다음과 같음.

```
HEADER.PAYLOAD.SIGNATURE
```

<br>

<br>

**Header**

HEADER는 `JWT를 검증하는 데 필요한 정보`를 담고 있음.

- Signature에 사용한 암호화 알고리즘이 무엇인지
- Key의 ID가 무엇인지

이 정보를 Json → UTF-8 encoding → Base64 URL-Safe encoding 한 값이 들어가 있음. (암호화 X)

<br>

**Payload**

`인증에 필요한 데이터`를 저장함.

- 데이터의 각각 field를 `Claim`이라고 함.
- 대부분의 경우 Claim에 username을 포함함.
- 토큰 발행 시각(iat)과 토큰 만료 시각(exp)를 포함함.
- 원하는 Claim을 추가할 수 있음.
    > 하지만 민감정보는 포함시켜서는 안 됨.

이 정보도 Header와 마찬가지로 Json → UTF-8 encoding → Base64 URL-Safe encoding 한 값이 들어가 있음. (암호화 X)

<br>

**Signature**

token에 대한 진위 여부를 판단함.

- Header와 Payload를 합친 뒤 Secret Key로 Hash를 생성하여 암호화함. → 이를 Base64로 변경