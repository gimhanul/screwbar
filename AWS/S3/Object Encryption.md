# Object Encryption
## Server-Side Encryption (SSE)

### Amazon S3-Managed Keys (SSE-S3)
- enabled by default
- amazon s3에서 관리하는 키를 이용한 서버측 암호화
- 객체는 서버측에서 암호화됨
- 보안 유형은 AES-256
- Must set header **"x-amz-server-side-encryption": "AES256"**

### KMS Keys stored in AWS KMS (SSE-KMS)
- KMS 키를 이용해서 암호화 키를 관리함(키 관리 서비스)
- advantages: user control + audit key usage using CloudTrail (for logging)
- Must set header **"x-amz-server-side-encryption": "aws:kms"**
- Limitations
	- when you upload, it calls the **GenerateDataKey** KMS API
	- when you download, it calls the **Decrypts** KMS API

### Customer-Provided Keys (SSE-C)
- 고객이 제공한 키를 사용함
- 외부에서 키를 사용하지만 서버 사이드인 이유는 키를 AWS로 전송하기 때문임
- 하지만 Amazon S3는 제공받은 키를 절대 저장하지 않음(사용 후 폐기)
- **HTTPS must be used**
- Encryption key must provided in HTTP headers, for every HTTP request made

## Client-Side Encryption (CSE)
클라이언트측의 모든 것을 암호화한 뒤에 Amazon S3에 업로드함

- Use client libraries such as **Amazon S3 Client-Side Encryption Library**
- 암호화 해서 보냄 -> 받아서 복호화함
- Customer fully manages the key and encryption cycle

## Encryption in transit (SSL/TLS)
- Encryption in flight is also called SSL/TLS
- Amazon S3 exposes two endpoints:
	- HTTP Endpoint - non encrypted
	- HTTPS Endpoint - encryption in flight
- HTTPS is recommended

### Force Encryption in Transit aws:SecureTransport
버킷 정책에 aws:SecureTransport를 false로 설정하면 HTTP를 사용하려는 모든 사용자가 차단됨