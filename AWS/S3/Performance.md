# Baseline Performance
- 요청이 아주 많을 때 자동으로 확장함
- 첫 번째 바이트를 수신하는 데 지연 시간도 100-200밀리초 사이로 아주짧음
- Your application can achieve at least 3500 PUT/COPY/POST/DELETE and 5500 GET/HEAD requests per second per prefix in a bucket
- There are no limits to the number of prefixes in a bucket
- object path => prefix
	- bucket/folder1/sub1/file => /folder1/sub1/
	- bucket/folder1/sub2/file => /folder1/sub2/
	- bucket/1/file => 1
	- bucket/2/file => 2
- 네 개의 prefix에 읽기 요청을 균등하게 분산하면 초당 22000개의 GET/HEAD 요청을 처리할 수 있음

# S3 Performance
- **Multi-Part upload**:
	- recommended for files > 100MB
	- must use for files > 5GB
	- 업로드를 병렬화하므로 전송 속도를 높여 대역폭을 최대화할 수 있음
	- 각 파일은 S3에 병렬로 업로드 되고 모든 파트가 업로드 되면 자동으로 모든 파트를 합쳐 다시 하나의 큰 파일로 만듦
- **S3 Transfer Acceleration**
	- 파일을 AWS 엣지 로케이션으로 전송해서 전송 속도를 높이고 데이터를 대상 리전에 있는 S3 버킷으로 전달함
	- 엣지 로케이션은 리전보다 수가 많음
	- 멀티파트 업로드와 같이 사용할 수 있음
	- File in USA ----(public www)---> Edge Location USA ----- (private AWS) ----> S3 Bucket Australia
- **S3 Byte-Range Fetches**
	- 파일에서 특정 바이트 범위를 가져오서 GET 요청을 병렬화함
	- 특정 바이트 범위를 가져오는 데 실패한 경우에도 더 작은 바이트 범위에서 재시도하므로 실패의 경우에도 복원력이 높음
	- 사용 사례: 다운로드 속도를 높일 떄, 파일의 일부만 검색할 떄