
# CNAME vs Alias

- AWS 리소스(Load Balancer, CoudFront...)를 사용하는 경우 hostname이 노출됨
- 보유한 도메인에 hostname을 매핑하고자 하는 경우

## CNAME
- hostname이 다른 hostname을 향하게 할 수 있음
	- app.mydomain.com => blabla.anyting.com
- **루트 도메인 이름이 아닌 경우에만 가능함** (aka. somthing.mydomain.com)
## Alias
- hostname이 특정 AWS 리소스로 향하게 할 수 있음
	- app.mydomain.com => blabla.amazonaws.com
- 루트 및 비루트 도메인 모두 가능
- 무료임
- 자체적으로 상태 확인이 가능함
- DNS 확장 기능(example.com -> LoadBalancer의 DNS name)
- 리소스의 IP가 바뀌는 것을 자동으로 인식함
- Zone Apex라는 DNS Namespage의 상위 노드로 사용될 수 있음(CNAME은 불가능)
- A / AAAA
- TTL을 설정할 수 없음 -> Route 53에 의해 자동으로 설정됨
- Alias Record Target
	- Elastic Load Balancers
	- CloudFront Distributions
	- API Gateway
	- Elastic Beanstalk environments
	- S3 Websites(not bucket)
	- VPC Interface Endpoints
	- Global Accelerator accelerator
	- Route 53 record in the same hosted zone
	 > EC2 DNS name 불가능
	 
	 