## 11-3. Map


`key`와 `value`로 구성된 Map.Entry 객체를 저장하는 구조를 가짐.

- key와 value는 모두 객체임.
- Entry는 Map 인터페이스 내부에 선언된 중첩 인터페이스임.

![Untitled 7](https://user-images.githubusercontent.com/80656733/150928749-f869c900-4f18-411c-b0bc-3fb7d448c715.png)

- key는 중복 저장 할 수 없지만 value는 중복 저장 할 수 있음.
- 기존에 저장된 key와 동일한 key로 값을 저장하면 기존의 값은 없어지고 새로운 값으로 대체됨.