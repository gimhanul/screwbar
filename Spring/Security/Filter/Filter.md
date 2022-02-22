## 2-4. Filter

Filter는 `요청 전과 응답 후 어떤 작업`을 하도록 하는 것임.

![image](https://user-images.githubusercontent.com/80656733/155106878-d64ba544-8ddf-489d-adc6-816bcde7541b.png)

Spring Security의 동작은 사실상 Filter로 동작한다고 해도 무방함.

- 다양한 Filter들이 각자 다른 기능을 함.
    > Filter가 어떤 기능을 하는지 알기 위해서는 Filter의 doFilter method를 살펴보면 됨.

- 이런 Filter들은 제외할 수도, 추가할 수도 있음.

- Filter에 동작하는 순서를 정해줄 수 있음.

<br>

Filter가 여러 개 일 때, 다음과 같이 동작함.
![image](https://user-images.githubusercontent.com/80656733/155108797-6fa23fe8-cc66-4514-a3a4-e8dc4cf33e19.png)
