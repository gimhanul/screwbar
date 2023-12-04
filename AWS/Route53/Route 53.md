# Route 53
- 고가용성, 확장성, 완전히 관리되며, 권한 있는 DNS
	- 권한이 있는 = 고객이 직접 DNS Record를 완전히 제어할 수 있음
- Domain Registrar임
- 리소스 상태를 확인할 수 있음
- 100% SLA 가용성을 제공하는 유일한 AWS 서비스임
### 왜 Route 53일까?
53은 DNS 서비스에서 사용되는 전통적인 DNS 포트임

## Records
- 특정 도메인으로 라우팅하는 방법을 정의함
- 각각의 Record는 다음을 포함함:
	- **Domain/subdomain Name**: e.g., example.com
	- **Record Type**: e.g., A or AAAA
	- **Value**: e.g., 123.456.789.123
	- **Routing Policy**: Route 53이 쿼리에 응답하는 방식
	- **TTL**: Time To Live; Record가 캐싱되는 시간
### DNS Record Types
- **A**: hostname을 IPv4 주소를 매핑함
- **AAAA**: hostname을 IPv6 주소를 매핑함
- **CNAME**:hostname을 다른 hostname과 매핑함
	- 대상 hostname은 A나 AAAA Record가 될 수 있음
	- 상위 노드에 대한 CNAME record를 만들 수 없음 (Zone Apex)
		- example.com - X
		- www.example.com - O
- **NS**: Name Server의 DNS 이름 또는 IP 주소로 호스팅 존에 대한 DNS 쿼리에 응답
	- 트래픽이 도메인으로 라우팅 되는 방식을 제어함

## Hosted Zones
- 레코드의 컨테이너
- 도메인과 서브도메인으로 가는 트래픽의 라우팅 방식을 정의함
- $0.50 / month
### Types
- **Public Hosted Zones**: 퍼블릭 도메인 이름을 살 때마다 퍼블릭 호스팅 존을 만들 수 있음
	- 쿼리에 도메인 이름의 IP가 무엇인지 알 수 있음
- **Private Hosted Zones**: 공개되지 않은 도메인 이름을 지원함
	- 가상 프라이빗 클라우드 (VPC)만이 URL을 resolve할 수 있음
	- e.g., 회사 네트워크 내에서만 접근할 수 있는 URL

## Domain Registar vs. DNS Service
- 도메인을 타사 등록 대행사에서 구매해도 DNS 서비스 제공자로 Route 53을 사용할 수 있음
- 사용하려면 Route 53에서 Public Hosted Zone을 생성한 뒤 도메인을 구매한 타사 웹사이트에서 Name Server or NS를 업데이트 하면 Route 53의 Name Server를 가르키게 됨
