# Time To Live (TTL)

![](https://velog.velcdn.com/images/gagaeun/post/c6e47f2b-7acf-4ac8-96d3-0df7d42b51d7/image.png)

- High TTL -  e.g., 24 hr
	- Route 53의 트래픽 현저히 적음
	- 클라이언트가 오래된 레코드를 받을 가능성 있음
	- 레코드를 바꾸고자 한다면 모든 클라이언트가 새 레코드를 캐시에 저장할 때까지 24시간을 기다려야 함
- Low TTL - e.g., 60 sec
	- DNS에는 트래픽 양이 많아져 많은 비용이 들음
	- 오래된 레코드의 보관 시간이 짧아짐
	- 레코드 변경이 빨라짐 = 레코드 변경 용이

> 어떤 설정이 더 적합한지는 상황에 따라 다름

- TTL은 모든 레코드에 있어서 필수적임 (단, 별칭 레코드는 제외)