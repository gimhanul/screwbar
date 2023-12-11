# Static Website Hosting
- 웹 사이트를 호스팅하고 인터넷에서 액세스할 수 있게 만들 수 있음
- The website URL will be (depending on the region)
	- http://**bucket-name**.s3-website-**aws-region**.amazonaws.com
	- http://**bucket-name**.s3-website.**aws-region**.amazonaws.com
- 403 Forbidden이 뜬다면, make sure the bucket policy allows public reads!