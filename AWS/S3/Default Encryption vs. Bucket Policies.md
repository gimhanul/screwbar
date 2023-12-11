# Default Encryption vs. Bucket Policies
- 모든 버킷은 SSE-S3 암호화가 기본으로 설정되어 있음 -> 변경 가능
- 버킷 정책을 이용해서 암호화를 강제하고 올바른 암호화 헤더가 없는 경우 API 요청을 거절할 수 있음

> Bucket Policies are evaluated before Default Encryption