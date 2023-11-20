# Storage Options

## EBS Volume
- Elastic Block Store
- 인스턴스가 실행 중인 동안 연결 가능한 네트워크 드라이브
- 인스턴스 종료 후에도 데이터를 지속할 수 있음
- 인스턴스 재생성 후 이전 EBS Volume을 마운트하면 데이터를 다시 받을 수 있음
- CCP Level에서는 하나의 EBS는 하나의 EC2 인스턴스에 마운트 가능
	- 인스턴스 하나에 EBS Volume이 두 개 연결되는 것은 가능함
	- 인스턴스 1개 : EBS Volume N개
	- 꼭 연결되지 않아도 됨
- 특정 가용 영역에 고정
- 쉽게 생각하면 네트워크 USB 스틱이라고 생각하면 됨
	- 실제로 물리적은 연결은 없지만 네트워크를 통해 연결
- 무료 등급으로는 매달 30GB의 EBS Storage를 범용 SSD 또는 마그네틱 유형으로 제공됨
- 인스턴스와 EBS Volume이 통신을 하기 위해서는 네트워크가 필요함
- 따라서 지연이 생길수도 있음
- 미리 용량을 결정해야 함
- 미리 단위 초당 전송 수를 지정해야 함(IOPS)
- EC2 인스턴스를 통해 EBS Volume을 생성하는 경우 **종료시 삭제**라는 속성이 있음
	- root default: 함꼐 삭제
	- others default: 함께 삭제 X
- 
### CCP Level
하나의 EBS는 하나의 EC2 인스턴스에 마운트 가능
### Associate Level
일부 EBS 다중 연결
