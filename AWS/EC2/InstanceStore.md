# EC2 Instance Store
- EBS Volume은 네트워크 드라이브라서 성능에 제한이 있음
- **성능 향상을 위해선, 하드웨어 디스크 성능이 향상되어야 함**
- EC2 Instance Store는 물리적 서버에 하드웨어 드라이브를 물고 있음
- I/O 성능 향상
- Instance Store를 중지 또는 종료하면 해당 Storage는 손실됨
	- 그래서 임시 Storage라고 부름
	- 장기적인 Storage는 될 수 없음
- 활용 예시
	- 버퍼나 캐시
	- 스크래치 데이터 또는 임시 콘텐츠를 사용하려는 경우
- EC2 Instance와 기본 서버에 장애가 발생하면 연결된 하드웨어에도 장애가 발생하므로 데이터 손실에 위험이 존재함
	- 따라서 데이터를 백업하거나 복제해둬야 함