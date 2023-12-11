# Event Notifications
- Events: S3:ObjectCreated, S3:ObjectRemoved, S3:ObjectRestored, S3:Replication...
- Object name filtering possible (*.jpg)
- Use case: 특정한 이벤트에 자동으로 반응하려는 경우
- **can create as many "S3 events" as desired
- 거의 몇 초 안으로 전달되지만 간혹 몇 분 정도 걸릴 수도 있음
- IAM 권한을 갖고 있어야 함
- SNS, SQS, Lambda Function are the target of event notifications
- All Events -> EventBridge -> SNS, SQS, or Lambda Function
