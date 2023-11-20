# Amazon Machine Image
- EC2 Instance를 통해 만든 Image
- you can add your own software, configuration, operating system, monitoring...
- 부팅 및 설정에 드는 시간 단축
- EC2 Instance에 설치하고자 하는 모든 Software를 AMI가 미리 패키징해주기 때문임
- 특정 지역에서 구축한 다음 다른 지역으로 복사해서 활용 가능
- 종류
	- Public AMI: AWS가 제공함(Amazon Linux2)
	- 자체적으로 구성할 수 있음: 유지, 관리 직접 해야 함
	- AWS Marketplace AMI: 다른 사람이 구축한 이미지 사용, 보통은 구매한 것
## Processing
1. EC2를 원하는대로 설정함
2. Instance를 중지해 데이터 무결성을 확보함
3. 이를 바탕으로 AMI를 구축함
4. 이 과정에서 EBS Snapshot 생성
5. 완료