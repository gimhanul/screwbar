# Load Balancer
> 트래픽을 여러 개의 서버로 전달하는 역할을 함

- 부하를 다수의 다운스트림 인스턴스로 분산하기 위함
- 애플리케이션에 단일 액세스 지점 DNS를 노출하게 됨
- 다운스트림 인스턴스의 장애를 원활히 처리할 수 있음
- 로드밸런서가 상태 확인 메커니즘으로 어떤 인스턴스로 트래픽을 보낼 수 없는지 확인해줌
- SSL 종료를 할 수 있음
- [쿠키로 고정도](https://www.imperva.com/learn/availability/sticky-session-persistence-and-cookies/)를 강화할 수 있음
- 영역에 걸친 고가용성을 가짐
- 클라우드 내에서 개인 트래픽과 공공 트래픽을 분리할 수 있음

# Elastic Load Balancer
- **관리형** 로드 밸런서
	- 어떤 경우에도 작동할 것을 보장함
	- AWS가 업그레이드, 유지 관리, 고가용성을 책임짐
	- 작동 방식을 수정할 수 있게끔 일부 구성 놉을 제공함
- 무조건 쓰는 편이 좋음
	- 자체 로드 밸런서를 마련하는 것보다 저렴함
	- 자체 로드 밸런서를 직접 관리하려면 확장성 측면에서 번거로움
	- 다수의 AWS 서비스들과 통합되어 있어 편리함
- 일부 로드 밸런서들은 내부에 설정될 수 있어 네트워크에 개인적인 접근이 가능함
- 웹사이트와 공공 애플리케이션 모두에 사용이 가능한 외부 공공 로드 밸런서도 있음

## Clasic Load Balancer(CLB)
- v1 - old generation - 2009
- HTTP, HTTPS, TCP, SSL, secure TCP 지원
- 더 이상 권장하지 않음
- 사용이 가능하긴 함
## Application Load Balancer(ALB)
- v2 - new generation - 2016
- HTTP, HTTPS, WebSocket 지원
## Network Load Balancer(NLB)
- v2- new generation - 2017
- TCP, TLS (secure TCP), UDP 지원
## Gateway Load Balancer(GWLB)
- 2020
- 네트워크 층에서 작동함(3계층, IP 프로토콜)

# Load Balancer Security Groups
EC2 인스턴스는 로드 밸런서를 통해 곧장 들어오는 트래픽만을 허용해야 하기 때문에 EC2 인스턴스의 보안 그룹 규칙은 조금 달라야 함
소스가 IP 범위가 아니라 보안그룹이 됨
EC2 인스턴스의 보안 그룹을 로드 밸런서의 보안 그룹으로 연결하는 것임
