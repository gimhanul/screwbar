# Health Checks
- 주로 공용 리소스에 대한 상태를 확인하는 방법임
- 세 가지의 상태 확인 가능:
	- 공용 엔드 포인트 모니터링(application, server, other AWS resource)
	- 다른 상태확인을 모니터링하는 상태 확인 = 계산된 상태 확인(Calculated Health Checks)
	- CloudWatch 경보의 상태를 모니터링하는 상태 확인 
		- 제어가 쉽고 개인 리소스에 유용함
- 상태 확인은 각자의 메트릭을 사용함

## Monitor an Endpoint
- 15개의 global health checkers가 endpoint의 상태를 확인함
	- 간격을 설정할 수 있음 - 30초
	- 빠른 상태 확인 - 10초 (비용 up)
	- HTTP, HTTPS, TCP 등 많은 프로토콜을 지원함
	- 18% 이상의 상태 확인이 endpoint를 정상이라고 판단하면 Route 53도 이를 정상이라고 간주함
	- 위치를 선택할 수 있음
- 2xx, 3xx 코드를 받아야 통과됨
- 텍스트 기반의 응답일 경우 앞 5120bytes를 확인해 응답 자체에 해당 텍스트가 있는지 확인함
- 상태 확인이 작동 가능하려면 health checkers가 application balancer나 endpoint에 접근이 가능해야 함
	- 따라서 상태 확인 IP 주소 범위에서 들어오는 모든 요청을 허용해야 함

## Calculated Health Checks

![](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQfmlyYu_JxUq1ZXicR7Zl4a1gCeGykSVM_VnbE9KtqUIM9b9yQtP_-taT3tYtubBJh7_8&usqp=CAU)

- 여러 개의 상태 확인 결과를 하나로 합쳐줌
- 합치기 위한 조건으로 OR, AND, NOT 사용 가능
- 하위 상태 확인을 256개까지 모니터링할 수 있음
- 상위 상태 확인이 통과하기 위해 몇 개의 상태 확인을 통과해야 하는지 지정할 수 있음

## Private Hosted Zones
- Route 53의 상태 확인이 공용 웹에 있기 때문에 VPC 욉에 있음
- 즉, privat eendpoint에 접근이 불가능함(private VPC or on-premises resource)
- CloudWatch 지표를 만들어 CloudWatch 알람을 할당하는 식으로 문제 해결
- CloudWatch 매트릭을 이용해 개인 서브넷 안에 있는 EC2 인스턴스를 모니터함
