## 3-1. Runtime Data Area


### 3-1-1. Method Area

JVM이 시작할 때 생성되고 모든 스레드가 공유하는 영역. 코드에서 사용되는 `클래스`들을 클래스 로더로 읽어 클래스별로 static field(정적 필드), constant(상수), method code(메소드 코드), constructor code(생성자 코드) 등을 분류해서 저장함.

### 3-1-2. Heap Area

`객체와 배열이 생성`되는 영역. 생성된 객체와 배열은 JVM Stack Area의 변수나 다른 객체의 Field에서 참조함. 만일 참조하는 변수나 필드가 없다면 의미 없는 객체가 되기 때문에 `Garbage Collector` 를 실행시켜 자동으로 제거함.

### 3-1-3. JVM Stack Area

`method`를 호출할 때마다 `프레임`을 추가(push)하고 method가 종료되면 해당 프레임을 제거(pop)함.

프레임 내부에는 `로컬 변수 스택`이 있음. 변수가 추가되거나 제거됨.