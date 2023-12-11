# MFA Delete
- **MFA (Multi-Factor Authentication)**
	- 사용자가 장치에서 코드를 생성하도록 강제함
	- google authenticator application이 있는 폰이나 MFA 하드웨어 장치 등
	- 중요한 작업을 수행하기 전에 코드를 삽입해야 함
- MFA will be required:
	- Permanently delete an object version
	- Suspend Versioning on the bucket
- MFA won't be required to:
	- Enable Versioning
	- List deleted versions
- 
> MFA Delete를 사용하려면 **Versioning must be enabled** on the bucket
> 버킷 소유자, 루트 계정만 할 수 있음

