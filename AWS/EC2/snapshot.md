# EBS Snapshots
- 특정 시점에 대한 백업
- 권장사항
- EBS Snapshot은 다른 가용 영역이나 다른 리전에 복사할 수 있음
## Features
### EBS Snapshot Archive
- 최대 75% 저렴하게 snapshot을 옮길 수 있음
- Archive를 복원하는 데 24~72시간 소요됨
### Recycle Bin for EBS Snapshots
- EBS Snapshot을 삭제할 때 영구삭제를 하지 않고 휴지통에 넣음
- 휴지통에 보관되는 기간은 1일 ~ 1년 사이로 설정할 수 있음
### Fast Snapshot Restore(FSR)
- 스냅샷을 완전 초기화해 첫 사용에서의 지연 시간을 없앰
- 비용이 많이 들음
- 스냅샷이 아주 크고 EBS Volume 또는 EC2 Instance를 빠르게 초기화해야 할 때 유용함
- 