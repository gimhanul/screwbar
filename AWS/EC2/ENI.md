# Elastic Network Interfaces (ENI)
- VPC의 논리적 구성 요소
- 가상 네트워크 카드
- EC2 인스턴스가 네트워크에 액세스하도록 도움
- EC2 인스턴스 외부에서도 사용됨
- EC2 인스턴스와 독립적으로 ENI를 생성하고 즉시 연결할 수 있음
- 장애 조치를 위해 EC2 인스턴스에서 이동시킬 수 있음
- 특정 가용 영역에 바인딩됨(특정 AZ에서만 바인딩 가능)
## can have the following Attributes:
- 사설 IPv4와 하나 이상의 보조 IPv4를 가질 수 있음
- 하나의 사설 IPv4에 하나의 Elastic IP
- 하나의 공용 IP에 하나의 Elastic IP
- 하나 이상의 보안 그룹 연결
- Mac 주소 및 기타 항목 연결
