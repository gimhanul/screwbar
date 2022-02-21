## 1-5. Resource

java.net.URL 의 한계(classpath 내부 접근이나 상대경로 등)를 넘어서기 위해 스프링에서 추가로 구현함.

### Resource Interface

```java
public interface Resource extends InutStreamSource {
	boolean exists();
	boolean isReadable();
	boolean isOpen();
	boolean isFile();

	URL getURL() throws IOException;
	URI getURI() throws IOEXception;
	File getFile() throws IOException;
	ReadableByteChannel readableChannel() throws IOException;
	
	long contentLength() throws IOException;
	long lastModified() throws IOException;
	
	Resouce createRelative(String relativaPath) throws IOException;
	String getFilename();
	String getDescription();
}
```