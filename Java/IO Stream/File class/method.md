### 12-13-2. 메소드

exists 메소드 리턴값과 상관 없이 다음 메소드로 파일 또는 폴더를 생성할 수 있음.

| 리턴 타입 | 메소드 | 설명 |
| --- | --- | --- |
| boolean | createNewFile() | 새로운 파일 생성 |
| boolean  | mkdir() | 새로운 폴더 생성 |
| boolean | mkdirs() | 경로상에 없는 모든 폴더 생성 |

<br>

<br>

exists() 메소드 리턴값이 true일 때 (→ 파일이나 폴더가 존재할 때) 다음 메소드를 사용할 수 있음.

| 리턴 타입 | 메소드 | 설명 |
| --- | --- | --- |
| boolean | delete() | 파일 또는 폴더 삭제 |
| boolean | canExecute() | 실행할 수 있는 파일인지 여부 확인 |
| boolean | canRead() | 읽을 수 있는 파일인지 여부 확인 |
| boolean | canWrite() | 수정 및 저장할 수 있는 파일인지 여부 확인 |
| String | getName() | 파일의 이름 return |
| String | getparent() | 부모 폴더 return |
| File | getParentFile() | 부모 폴더를 File 객체로 생성 후 return |
| String | getPath() | 전체 경로 return |
| boolean | isDirectory() | 폴더인지 여부 확인 |
| boolean | isFile() | 파일인지 여부 확인 |
| boolean | isHidden() | 숨긴 파일인지 여부 확인 |
| long | lastModified() | 마지막 수정 날짜 및 시간 return |
| long | length() | 파일의 크기 return |
| String[] | list() | 폴더에 포함된 파일 및 서브 폴더 목록 전부 return |
| String[] | list(FilenameFilter filter) | filter에 맞는 것만 list() |
| File[] | listFiles() | 폴더에 포함된 파일 및 서브 폴더 목록 전부 return |
| File[] | listFiles(FilenameFilter filter) | filter에 맞는 것만 listFiles() |

👉🏻 [예제](https://github.com/gimhanul/Java/blob/master/src/input_output_api/FileTest.java)