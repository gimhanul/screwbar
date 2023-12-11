# Cross-Origin Resource Sharing (CORS)
- Origin = schema (protocol) + host (domain) + port
- 웹 브라우저 기반 보안 메커니즘
- 메인 오리진을 방문하는 동안 다른 오리진에 대한 요청을 허용하거나 거부함
- 오리진이 같다는 것 => 프로토콜, 호스트, 포트가 같음
- 다른 오리진이 CORS 헤더를 사용해서 요청을 허용하지 않는 한 요청은 이행되지 않음
- 이를 **Access-Control-Allow-Origin** 헤더라고 함

![](https://miro.medium.com/v2/resize:fit:1400/0*CYccqYeAzYbLmwR3.png)

# S3 CORS
- client가 s3 bucket에서 cors request를 보내면 정확한 cors 헤더를 활성화해야 함
- you can allow for a specific origin or for * (all origins)
