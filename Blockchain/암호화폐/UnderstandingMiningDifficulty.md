## 2.3. Understanding Mining Difficulty

난이도 = 현재 대상 / 최대 대상

```text
Total possible 64-digit hexadecimal numbers:
16 x 16 x ...... x 16 = 16^64 = 10^77

Total valid hashes (with 18 leading zeros):
16 x 16 x ...... x 16 = 16^(64-18) = 2 x 10^55

Probability that a Randomly picked hash is valid:
2 x 10^55 / 10^77 = 2 x 10^(-22) = 0.00000000000000000002%
```
