# Replication
- **Must enable Versioning** in source and destination buckets
- Cross-Region Replication (CPR)
- Same-Region Replication (SRR)
- 서로 다른 계정 간에도 사용할 수 있음
- 복제는 비동기식으로 백그라운드에서 이루어짐
- iAM에 S3 읽기, 쓰기 권한을 부여해야 함

- Use Cases:
	- **CRR** - compliance, lower latency access, replication across accounts
	- **SRR** - log aggregation, live replication between production and test accounts

## S3 Batch Replication
복제를 활성화한 후에는 새로운 객체만 복제 대상이 됨
-> 기존의 객체부터 복제에 실패한 객체까지 복제할 수 있는 기능

> 작업을 삭제하려면
> **can replicate delete markers** from source to target (optional setting)
> Deletions with a version ID are not replicated (to avoid malicious deletes)

> **There is no "chaining" of replication**

