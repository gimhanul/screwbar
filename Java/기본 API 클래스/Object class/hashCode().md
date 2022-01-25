### 9-1-2. hashCode()

해시코드란 객체를 식별하는 하나의 정수값을 말함.

- 기존 hashCode()는 가장 먼저 return된 해시 코드 값이 같은지를 보고, 해시코드 값이 다르면 다른 객체로 판단, 해시코드 값이 같으면 equals() 메소드로 다시 비교해서 이것도 같아야 동등 객체로 봄.
- Object 클래스의 hashCode() 메소드는 객체의 메모리 번지를 이용해서 해시코드를 만들어 return하기 때문에 객체마다 다른 값을 가짐.
- 논리적 동등 비교시 hashCode()를 overiding할 필요가 있음.

👉🏻 [예제](https://github.com/gimhanul/Java/tree/master/src/basic_api_class/object/hash_code)