## instanceof 연산자

*인스턴스는 클래스를 통해 만들어진 객체라고 했다. instanceof 연산자는 만들어진 객체가 특정 클래스의 인스턴스인지 물어보는 연산자다. instanceof 연산자는 결과로 true 또는 false를 반납한다. 사용법은 아래와 같다.*

```java
package instanceof03;

interface 날수있는 {
}

class 박쥐 implements 날수있는 {
}

class 참새 implements 날수있는 {
}

public class Driver {
  public static void main(String[] args) {
    날수있는 박쥐객체 = new  박쥐();
    // 새로운 박쥐가 태어나니 날수있는 역할을 하는 "박쥐객체"로 이름 지음
    날수있는 참새객체 = new  참새();
    // 새로운 참새가 태어나니 날수있는 역할을 하는 "참새객체"로 이름 지음

    System.out.println(박쥐객체 instanceof 날수있는);
    System.out.println(박쥐객체 instanceof 박쥐);

    System.out.println(참새객체 instanceof 날수있는);
    System.out.println(참새객체 instanceof 참새);
```
> 실행 결과는 모두 true를 반환한다.

