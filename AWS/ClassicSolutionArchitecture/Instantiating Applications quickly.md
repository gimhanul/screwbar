# Instantiating Applications quickly
full stack application을 세팅하는 것은 시간이 오래 걸림
어떻게 하면 빨리 할 수 있을까?

## EC2
- **Golden AMI**: application과 OS 종속성 등 모든 것을 사전에 설치하고 그것으로부터 AMI를 생성하는 것, 이후 모든 인스턴스를 Golden AMI로 직접 실행하면 됨
- **User Data**: 사용자 데이터로 인스턴스 부트스트랩, 느림
- **Hybrid**: Golden AMI, User Data 합침

## RDS
- **Restore from a Snapshot**

## EBS Volume
- **Restore from a Snapshot**

