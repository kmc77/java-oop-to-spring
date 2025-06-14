## 다형성: 사용편의성
*상위 클래스와 하위 클래스 사이에서도 다형성을 이야기할 수 있고, 인터페이스와 그것의 구현 클래스 사이에서도 다형성을 이야기할 수 있지만 "가장 기본은 오버라이딩과 오버로딩이라고 할 수 있다."*

### 오버라이딩 - 재정의
- 상위 클래스의 메서드와 같은 메서드 이름, 같은 인자 리스트

### 오버로딩 - 중복정의
- 같은 메서드 이름, 다른 인자 리스트

### 다형성과 T메모리
주목할 것은 pingu 객체 참조 변수는 타입이 Animal(상위 클래스) 타입이라는 것이다. 그럼에도 Animal 객체의 ShowName()은 Penguin(하위 클래스) 객체의 ShowName() 에 의해 가려져(오버라이딩:재정의) 있다.
따라서, pingu.ShowName() 메서드를 실행하면 Aninal(상위 클래스) 객체에 정의된 ShowName() 메서드가 아닌 Penguin(하위 클래스) 객체에 의해 재정의(오버라이딩)된 ShowName() 메서드가 실행된다.

*상위 클래스 타입의 객체 참조 변수를 사용하더라도 하위 클래스에서 오버라이딩(재정의) 한 메서드가 호출된다는 사실을 꼭 기억하자.*
