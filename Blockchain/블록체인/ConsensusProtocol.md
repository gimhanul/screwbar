## 1.7. Consensus Protocol

<br>

### 문제점

블록체인을 위한 합의 프로토콜로 두 가지 문제를 해결해야 함.

1. Attackers

    공격자로부터 네트워크를 보호하는 것. 가운데 낑겨있는 블록을 수정하는 것이 아닌, **악성 블록을 새로 추가하고자 할 때**를 이야기함.

2. Competing Chains

    블록체인의 경쟁 체인 문제. 전세계 단위로 보았을 때 블록을 추가할 때 지연이 발생할 수 있음. 또한 서로 멀리 떨어진 두 노드가 **동시에 채굴에 성공**할수도 있음.

<br>

### 종류

- 작업 증명 `Proof-of-Work, PoW`
- 지분 증명 `Proof-of-Stake, PoS`
- Other

<br>

### Attackers

채굴자가 새로운 블록을 추가할 때 악의적인 블록인지를 엄격하게 검사함.

> 적합한 블록이라면 대가를 주고, 아니라면 패널티를 줌.

<br>

### Competing Chains

**가장 긴 체인**이 이김. 어느쪽이든 블록이 먼저 추가되면, 그 체인의 다른 체인을 교체함.

즉, 50% 이상의 해싱 파워를 가진 체인이 이김.

> **해싱 파워**: 초당 얼마나 많은 해시를 확인하느냐

진 블록은 고아 블록 `Orphaned Block`이 됨.