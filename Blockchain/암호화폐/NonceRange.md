## 2-5. Nonce Range

Nonce 는 32bit unsigned number 로 0 ~ 40억까지 값이 들어갈 수 있음.

Difficulty: 2 x 10^(-22)

Nonce: 

```text
The Nonce is a 32-bit number, the Max Nonce:
2^32 = 4 x 10^9

Assuming no collisions, this means 4 * 10^9 different hashes
Probability that ONE of them will be valid:
4 x 10^9 x 2 x 10^(-22) = 8 x 10^(-13) = 10^(-12) = 0.0000000001%
```

> 즉, 하나의 논스 범위는 충분하지 않음.

<br>

### Timestamp

사실은 블록체인에 timestamp 필드가 하나 더 있음.

1초마다 timestamp 필드값이 바뀌기 때문에 nonce 값을 아무리 검사해도 1초마다 해시 값이 바뀜.