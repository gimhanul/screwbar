# Amazon EFS - Elastic File System
- 관리형 Network File System(NFS)
- 많은 EC2 Instance에 마운트될 수 있음
- EC2 Instance는 서로 다른 가용 영역에 있을 수 있음
- 가용성이 높음
- 확장성이 뛰어남
- 비쌈(gp2 EBS volume의 3배)
- 사용량에 따라 비용을 지불함 -> 미리 용량 프로비저닝할 필요 없음
- 사용 사례
	- 콘텐츠 관리
	- 웹 서빙
	- 데이터 공유
	- Wordpress
- 내부적으로 NFS Protocol을 사용함
- 액세스를 제어하려면 보안 그룹을 설정해야 함
- **Linux 기반의 AMI와만 호환됨**
- KMS를 사용해서 미사용 암호화를 활성화할 수 있음
- 표준 파일 API를 가진 POSIX file System을 사용함
- EFS 스케일은 동시 NFS Client 수천 개와 10GB 이상의 처리량을 확보할 수 있음
- PG 규모의 네트워크 파일시스템으로 자동 확장할 수 있음
- 네트워크 파일 시스템 생성 시 성능 모드를 지정할 수 있음
## Performance Mode
### General Purpose(default)
- 지연 시간에 민감한 사용 사례에 사용됨
- 웹 서버 or CMS
### MAX I/O
- 처리량 및 병렬성이 높음
- 빅데이터 애플리케이션이나 미디어 처리가 필요한 경우 유용함
## Throughput Mode
### Bursting
- 1TB = 50MiB/s + burst of up to 100MiB/s
### Provisioned
- Storage  크기에 관계 없이 처리량을 설정하고 싶은 경우
- 1TB의 Storage에서 초당 1GiB 처리 가능
- Storage와 처리량을 분리함
### Elastic
- 워크로드에 따라 처리량을 자동으로 조절
- 워크로드를 예측하기 어려울 때 유용함
# EFS - Storage Classes
## Storage Tiers 
- Storage 계층을 설정할 수 있음
- 며칠 후 파일을 다른 계층으로 옮길 수 있음
	- 사용 빈도에 따라 적절한 계층에 두면 비용을 절감할 수 있음
## Availability and Durability
> 가용성과 내구성
### Standard
- 다중 AZ로 설정
- 프로덕션 사용 사례에 적합
### One Zone
- 하나의 AZ에만 있음
- 개발용으로 적합
- 백업은 기본적으로 활성화되도록 설저오딤
- 액세스 빈도가 낮은 Storage 계층과 호환되지 않음
- 따라서 EFS One Zone IA라고 불림
- 할인이 많이 됨 90% 정도 -> 비용 절감
- 