# S3 Storage Classes
객체를 생성할 때 클래스를 선택할 수도 있고 수동으로 수정할 수 있음
수명 주기 구성을 사용해 스토리지 클래스 간에 객체를 자동으로 이동할 수 있음

## Durability and Availability
### Durability
내구성 = S3로 인해 객체가 손실되는 횟수
99.999999999%의 내구성을 보장함
모든 스토리지 클래스의 내구성은 동일함

### Availability
가용성 - 서비스가 얼마나 용이하게 제공되는지
> S3 Standard의 가용성은 99.99%
> = 1년에 53분은 서비스를 이용할 수 없다는 의미
> = 몇 가지 에러가 발생한다

## S3 Standard
- 자주 액세스하는 데이터에 사용됨
- 기본적으로 사용하는 스토리지 유형
- 99.99% Availability
- 지연 시간 짧음
- 처리량 높음
- 두 개의 기능 장애를 동시에 버틸 수 있음
- 사례: 빅데이터 분석, 모바일, 게임 애플리케이션, 콘텐츠 배포

## S3 Infrequent Access (IA)
- 자주 액세스하지는 않지만 필요한 경우 빠르게 액세스해야 하는 데이터
- S3 Standard보다 비용이 적게 들지만 검색 비용 발생

- **Amazon S3 Standard-IA**
	- 99.9% Availability
	- 사례: 재해 복구, 백업
- **Amazon S3 One Zone-IA**
	- 단일 AZ 내에서는 높은 내구성을 갖지만 AZ가 파괴되면 데이터를 잃음
	- 99.5 Availability
	- 사례: 온프레미스 데이터 2차 백업, 재생성 가능한 데이터 저장

## S3 Glacier Storage Classes
- 콜드 스토리지
- 아카이빙과 백업을 위한 저비용 객체 스토리지
- Pricing: price for storage + object retrieval cost

- **Amazon S3 Glacier Instant Retrieval**
	- 밀리초 단위로 검색 가능
	- 분기에 한 번 액세스 하는 데이터에 아주 적합함
	- 최소 보관 기간이 90일
- **Amazon S3 Glacier Flexible Retrieval** (formerly Amazon S3 Glacier):
	- there are three options
		- Expedited: 1 to 5 minutes
		- Standard: 3 to 5 hours
		- Bulk: 5 to 12 hours, free
	- 최소 보관 기간이 90일
- **Amazon S3 Glacier Deep Archive - for long term storage:**
	- there two options
		- Standard: 12 hours
		- Bulk: 48 hours
	- 비용이 가장 저렴함
	- 최소 보관 기간이 180일

## S3 Intelligent-Tiering
- 사용 패턴에 따라 액세스된 티어 간에 객체를 이동할 수 있게 해줌
- 소액의 월별 모니터링 비용과 티어링 비용 발생
- 검색 비용 없음

- Frequent Access tier (automatic): default tier
- Infrequent Access tier (automatic): objects not accessed for 30 days
- Archive Instant Access tier (automatic): ~ for 90 days
- Archive Access tier (optional): configurable from 90 days to 700+ days