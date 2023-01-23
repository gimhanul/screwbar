## 1.1. What is a Blockchain?

### 시작

- Stuart Haber
- W.Scott Stornetta

<br>

### 정의

> A blockchain is a continuously growing list of records, called blocks, which are linked and secured using
> cryptography. - Wikipedia

> 지속적으로 증가하는 데이터, 즉 블록이라고 불리는 이 데이터를 암호학을 통해 보호하고 연결하는 기술.

<br>

### 블록의 구성 요소

| 요소         | 예시             | 설명        |
|------------|----------------|-----------|
| Data       | "Hello World!" | 데이터       |
| Prev.Hash  | 034DFA357      | 이전 블록의 해시 |
| Hash       | 4D56E1F05      | 데이터의 지문   |

<br>

### 블록체인의 구조

- Genesis Block
  - 블록체인의 첫 번째 블록임.
  - 절대 안 바뀜.
  - 이전 해시 없음.
- 다음 Block
  - 이전 블록의 해시를 참조함.

> 누군가 앞 블록의 데이터를 조작하면 해시가 바뀌기 때문에 다음 블록이 갖고 있는 해시와 매칭이 되지 않음.
> 따라서 다음 블록의 이전 해시를 보면 데이터의 조작 유무를 알 수 있음.