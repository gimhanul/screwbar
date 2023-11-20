# EBS Multi-Attach - io1 / io2 family
- 다중 연결 기능
- 하나의 EBS Volume을 같은 가용 영역에 있는 여러 EC2 Instance에 연결할 수 있게 해줌
- io1 / io2 제품군에서만 사용 가능
- 각 Instance는 고성능 Volume에 대한 읽기 및 쓰기 권한을 가짐(동시에 읽고 쓸 수 있음)
- 해당 가용 영역 내에서만 사용 가능
- 한 번에 16개의 EC2 Instance만 같은 Volume에 연결 가능
- 반드시 클러스터 인식 파일 시스템을 사용해야 함