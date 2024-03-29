# EBS Volume Types
## gp2 / gp3
- 범용 SSD Volume
- 다양한 워크로드에 대해 가격과 성능의 절충안
- 짧은 지연 시간
- 효율적인 비용
- 시스템 부팅 Volume에서 가상 데스크톱, 개발, 테스트 환경에서 사용 가능
- 크기는 1GB ~ 16TB로 다양함
### gp2
- Volume이 gp3에 비해 작음
- 최대 3000 IOPS 
	- 볼륨과 IOPS가 연결되어 있어서 볼륨 용량이 즈가하면 16000 IOPS까지 가능
### gp3
- 최신 세대 Volume
- 기본 성능으로 3000 IOPS / 초당 125MB 처리량 제공
- IOPS ~15000 / 처리량 ~1000MB/s 까지 증가시킬 수 있음
### gp2 vs gp3
gp3는 IOPS와 처리량을 독자적으로 설정할 수 있지만 gp2는 그 둘이 연결되어 있음
## io1 / io2
- 최고 성능 SSD Volume
- 미션 크리티컬(업무 수행을 위해 가장 중요한 요소)
- 지연시간 낮음
- 사용 사례
	- 대용량 워크로드에 쓰임
	- IOPS 성능을 유지할 필요가 있는 비즈니스 애플리케이션에 적합
	- 16000 IOPS 이상을 요하는 애플리케이션에 적합
	- 데이터베이스 워크로드에 적합
- Nitro EC2 Instance를 쓰는 경우에 최대 64000 IOPS까지 가능함
- 그게 아니라면 32000 IOPS
- IOPS를 스토리지 크기와 독립적으로 증가시킬 수 있음
### io1 vs io2
- 비용은 같으나 io2가 내구성과 기가 당 IOPS의 수가 더 높음
### io2
- 4GB ~ 64TB
- 고성능 유형의 볼륨
- 지연 시간이 ms 미만
- IOPS 대 GB 비율이 1000:1일 떄 최대 256000 IOPS
## st1
- 저비용 HDD Volume
- 잦은 접근과 처리량이 많은 워크로드에 쓰임
- 부팅 Volume일 수 없음
- 최대 16TB까지 확장
- 빅데이터나 데이터 웨어하우징 로그 처리에 적합
- 최대 처리량은 초당 500MB, 최대 IOPS는 500
## sc1
- 가장 비용이 적게 드는 HDD Volume
- 접근 빈도가 낮은 워크로드에 쓰임
- 부팅 Volume일 수 없음
- 최대 16TB까지 확장
- 아카이브 데이터용
- 최대 처리량은 초당 250MB, 최대 IOPS 250
# EBS Volume 정의 기준
- 크기
- 처리량
- IOPS(초당 I/O 작업 수)
# EC2 Instance
- gp2 / gp3 / io1 / io2만 부팅 Volume으로 사용될 수 있음(for root OS)
- 