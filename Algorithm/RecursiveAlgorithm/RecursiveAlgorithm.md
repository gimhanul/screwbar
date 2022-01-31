# 2. 순환 알고리즘

- 순환이란?
    
    어떤 알고리즘이나 함수가 `자기 자신을 호출`하여 문제를 해결하는 프로그래밍 기법임.
    

```c
//순환 알고리즘 예제
#include <stdio.h>

int func(int a) {
    if(a<=1) return 1;
    return func(a-1)+func(a-2);
}

int main() {
    int a=5;
    printf("%d", func(a));
    return 0;
}
```

위의 예제 코드에서는 피보나치 수열을 순환 알고리즘으로 구현하고 있음.

트리 형식으로 그려보면 밑과 같음.

![Untitled](https://user-images.githubusercontent.com/80656733/151806281-d329bbde-53d3-4ead-99ed-ba51234b16b2.png)

위 트리에서 종료 조건을 검토하며 계산하면 결과 값은 8이 나옴.