## interface, implements 키워드

Java에서 `interface`는 **행동(기능)의 명세(약속)**를 정의하는 틀임.  
`implements`는 해당 인터페이스의 기능을 **클래스에서 구현**할 때 사용됨.

```java
// 인터페이스 선언
public interface Animal {
    void sound();  // 추상 메서드 (몸체 없음)
}

// 인터페이스를 구현하는 클래스
public class Dog implements Animal {
    @Override
    public void sound() {
        System.out.println("멍멍!");
    }
}

// 실행 클래스
public class Main {
    public static void main(String[] args) {
        Animal myDog = new Dog(); // 업캐스팅
        myDog.sound();            // 출력: 멍멍!
    }
}
```

### 특징요약
- 인터페이스는 모든 메서드가 public abstract
- 인터페이스의 필드는 자동으로 public static final
- 인터페이스는 다중 구현 가능, 클래스는 단일 상속
- implements는 여러 인터페이스를 콤마(,)로 구분해 구현 가능

