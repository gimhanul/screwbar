### 1-1-1. HTTP Request 메시지 스펙

- 첫째줄: 요청 라인 -> HTTP 메서드(GET, PUT, POST 등)

- 둘째줄 ~ 줄바꿈 나오기 전까지: Header(User-Agent, Accept 등)

- 줄바꿈 이후: Request Body

```json
POST /create-developer HTTP/1.1
content-type: application/json
Accept: application/json

{
    "Key0": "value0",
    "Key1": "value1"
}
```