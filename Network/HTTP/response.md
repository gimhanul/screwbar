### 1-1-2. HTTP Response 메시지 스펙

- 첫째줄: 상태 라인(200, 500 등)

- 둘째줄 ~ 줄바꿈 나오기 전까지: Header

- 줄바꿈 이후: Request Body

```json
HTTP/1.1 200 OK
Content-Type: application/json
Transfer-Encoding: chunked
Date: Sat, 17 Jul 2021 15:33:34 GMT
Keep-Alive: timeout=60
Connection: keep-alive

{
    "Key0": "value0",
    "Key1": "value1"
}
```