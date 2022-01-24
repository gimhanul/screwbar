### 1-5-1. Resource 구현체

Spring 내부 Resource 구현체 중 대표적인 몇 가지

<br>
<br>

**UrlResource**

java.net.URL을 래핑한 버전, 다양한 종류(ftp:, file:, http:, 등의 prefix로 접근유형 판단)의 Resource에 접근 가능하지만 기본적으로는 http(s)로 원격 접근

<br>

**ClassPathResource**

classpath(소스코드를 빌드한 결과 → 기본적으로 target.classes 폴더) 하위의 Resource 접근 시 사용

<br>

**FileSystemResource**

File을 다루기 위한 Resource 구현체

<br>

**ServletContextResource, InputStreamResource, ByteArrayResource**

Servlet application 루트 하위 파일, InputStream, ByteArrayInput stream을 가져오기 위한 구현체