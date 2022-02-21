### 1-7-1. @NonNull annotation

해당 값이나 함수 등이 null이 아님을 나타내는 annotation.

org.springframework.lang.NonNull을 사용함.

<br>

- parameter에 붙이는 경우: null이 들어오는 것을 사전에 방지함.

```java
public void method(@NonNull String request) {
    //null check 필요 없음.
}
```

<br>

- property에 붙이는 경우: null을 저장할 수 없음.

```java
@NonNull
public String request = "REQUEST";
```

<br>

- method에 붙이는 경우: null을 return하는 경우 경고, 응답값을 저장하거나 활용하는 쪽이 NonNull이라고 신뢰할 수 있음.

```java
@NonNull
public String method(){
    //...
    return null; //불가능
}
```