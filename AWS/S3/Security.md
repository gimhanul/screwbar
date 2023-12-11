# Security
- **User-Based**
	- IAM Policies: 어떤 API 호출이 특정 IAM 사용자를 위해 허용되어야 하는지 승인함
- **Resource-Based**
	- Bucket Policies
		- S3 콘솔에서 할당
		- 전체 버킷 규칙
		- 특정 사용자가 들어올 수 있게 하거나 다른 계정의 사용자를 허용할 수 있음 = cross account
	- Object Access Control List (ACL): 세밀한 보안, 비활성화 가능함
	- Bucket Access Control List (ACL): 훨씬 덜 일반적임, 비활성화 가능함
- **Note**: IAM 원칙이 S3 객체에 액세스한다
	- IAM 권한이 허용하거나 Resource 정책이 이를 허용하는 경우
	- AND there's no explicit DENY
- **Encryption**: 암호 키를 사용하여 객체를 암호화

## Bucket Policies
- **JSON based policies**
	- Resources: buckets and Objects
	- Effect: Allow / Deny
	- Actions: Set of API to Allow or Deny
	- Principal: The account or user to apply the policy to
- Use S3 Bucket for policy to:
	- 버킷에 대한 공개 엑세스 허용
	- 업로드시 객체를 강제로 암호화
	- 또 다른 계정으로의 액세스 허용(cross account)

## Bucket settings for Block Public Access
기업 데이터 유출을 방지하기 위해 만들어진 설정임
S3 버킷 정책을 설정하여 공개로 만들더라도 이 설정이 활성화되어 있다면 버킷이 공개되지 않음
