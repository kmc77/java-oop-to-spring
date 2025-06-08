## final 키워드

*final은 마지막, 최종이라는 의미를 가진 단어다. final 키워드가 나타날 수 있는 곳은 딱 세 군데다. 사실 객체 지향 언어의 구성 요소는 딱 세 가지 뿐이다. 바로 클래스, 변수, 메서드다.*

```java
public final class 고양이 { }
//상송을 허락하지 않겠다는 의미
```

### 변수에 final이 붙었다면 어떤 의미?

*변경 불가능한 상수가 된다. 정적 상수는 선언 시에, 또는 정적 생성자에 해당하는 static 블록 내부에서 초기화가 가능하다. 객체 상수 역시 선언 시에, 또는 객체 상성자 또는 인스턴스 블록에서 초기화할 수 있다.*

### final과 메서드

*메서드가 final이라면 최종이니 재정의, 즉 오버라이딩을 금지하게 된다.*

```java
public class 동물 {
  final void 숨쉬다() {
    System.out.println("호흡 중");
    }
}

class 포유류 extends 동물 {
// 에러 발생: Cannot override the final method from 동물
void 숨쉬다() {
  System.out.println("호흡 중");
    }
}
//상송을 허락하지 않겠다는 의미
```
