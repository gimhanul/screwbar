## 4-11. Static Member

---

클래스에 고정된 멤버로서 객체를 생성하지 않고 사용할 수 있는 field와 method.

이들을 각각 `static field`, `static method`라고 함.

static memebr는 클래스에 고정된 멤버이므로 class loader가 바이트코드를 로딩해서 메소드 메모리 영역에 적재할 때 클래스별로 관리됨. 따라서 클래스 로딩이 끝나면 바로 사용할 수 있음.