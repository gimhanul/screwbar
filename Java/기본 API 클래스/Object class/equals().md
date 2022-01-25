### 9-1-1. equals()

`논리적으로 동등한지 비교`할 때 이용됨.

- equals() 메소드의 매개 타입은 Object로, 모든 객체가 매개값으로 대입될 수 있음.
    
    → 모든 객체는 Object 타입으로 promotion될 수 있기 때문임.
    
- Object 클래스의 equals() 메소드는 비교 연산자인 == 과 동일한 결과를 return함.
- 두 객체가 동일한 객체라면 true를 return하고, 그렇지 않으면 false를 return함.
- String 객체의 equals() 메소드는 String 객체의 번지를 비교하는 것이 아니라 문자열이 동일한지 조사함.
    
    → String 클래스가 Object 의 equals() 메소드를 overiding해서 번지 비교가 아닌 문자열 비교로 변경했기 때문임. 
    
- 일반적으로 Object의 equals() 메소드는 직접 사용되지 않고 하위 클래스에서 overiding하여 논리적으로 동등 비교할 때 이용됨.

👉🏻 [예제](https://github.com/gimhanul/Java/tree/master/src/basic_api_class/object/equals)