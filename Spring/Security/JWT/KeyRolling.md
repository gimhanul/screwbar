### 2-6-4. Key Rolling

JWT는 Secret Key가 노출되면 사실상 모든 데이터가 유출된다고 볼 수 있음.

이런 문제를 방지하기 위해 Secret Key를 여러 개 두고 Key 노출에 대비함.

`Secret Key를 여러 개 사용하고 수시로 추가, 삭제해서 변경하여 Secret Key를 안전한 상태로 두는 것`을 Key Rolling이라고 함.

- 필수로 해야 하는 것은 아님.
- 여러 개의 secret key가 존재하므로 header에 kid(secret key id)를 포함시킴.