# EBS Encryption
## EBS Volume을 생성할 때 일어나는 일
- 저장 데이터가 Volume 내부에 암호화됨
- Instance와 Volume간 전송 데이터가 암호화됨
- Snapshot이 암호화됨
> 암호화가 동시다발적으로 일어남
> 보이지 않게 처리되므로 아무것도 안 해도 됨
## 암호화
- 지연 시간에 영향이 거의 없음
- KMS에서 암호화 키를 생성해 AES-256 암호화 표준을 가짐
- Snapshot을 복사해 복호화한 걸 다시 암호화함
## 암복호화 방법
1. Volume의 EBS Snapshot을 생성함
2. 복사 기능을 통해 EBS Snapshot을 암호화함
3. Snapshot을 이용해 새 EBS Volume을 생성하면 해당 Volume도 암호화됨
4. 암호화된 Volume을 Instance 원본에 연결함
