# Elastic Beanstalk
- 다양한 애플리케이션과 환경을 갖고 있을 때 한 가지 방법으로 애플리케이션을 배포하길 원할 때 사용함
- 개발자 입장에서 애플리케이션을 AWS에 배포함
- 하나의 인터페이스에서 모든 컴포넌트(EC2, ASG, ELB, RDS, etc...)를 재사용함
- 개발자는 그냥 코드만 짜면 됨
- 간단하게 애플리케이션을 업데이트하는 방법도 제공됨
- 개발자가 모든 컴포넌트 설정에 대한 통제력을 가짐
- Beanstalk 자체는 무료, but 인스턴스나 ASG, ELB 등의 비용은 지불

## Components
- **Application**: 환경, 버전, 설정 등 Beanstalk 컴포넌트 컬렉션
- **Application Version**: 버전
- **Environment**
	- 환경에서 한 번에 하나의 애플리케이션 버전만 가질 수 있음
	- 버전 업데이트를 할 수 있음
	- **Tiers**: Web Server Environment Tier & Worker Environment Tier
	- 여러 환경을 만들 수 있음 (dev, test, qa, prod, etc...)
	- process
		1. Create Application
		2. Upload Version
		3. Launch Environment
		4. Manage Environment

## Supported Platform
- 엄청 많은 프로그래밍 언어를 지원함
- 없으면 커스텀 플랫폼을 만들 수 있음
- 그냥 모든 걸 배포할 수 있다고 보면 됨

## Deployment Modes
- Single Instance
	- Great for Dev
- High Availability with Load Balancer
	- Great for Prod
	- Multi AZ