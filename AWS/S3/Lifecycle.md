# Lifecycle Rules
스토리지 클래스 간에 객체를 옮길 때 Lifecycle 규칙을 이용해서 자동으로 옮길 수 있음

- **Transition Actions**: 다른 스토리지 클래스로 이전하기 위해 객체를 설정함
- **Expiration actions**: 일정 시간 뒤에 만료되어서 객체를 삭제하도록 설정함
	- can be used to delete old versions of files (if versioning is enabled)
	- can be used to delete incomplete Multi-Part uploads

- 규칙은 특정한 접두어에 대해 지정할 수도 있음(버킷 전체, 버킷 안의 특정한 경로에 적용)
- 특정한 객체 태그에 대해 규칙 지정 가능

## Storage Class Analysis
- 적절한 storage class로 objects를 옮기는 것을 도와줌
- Recommendations for Standard and Standard-IA
	- Does NOT work for One-Zone IA or Clacier