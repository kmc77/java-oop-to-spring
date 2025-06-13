## ISP - 인터페이스 분리 원칙 (Interface Segregation Principle)

> **클라이언트는 자신이 사용하지 않는 메서드에 의존해서는 안 된다.**  
> 즉, 인터페이스는 특정 클라이언트를 위한 최소한의 기능만 제공해야 한다.

---

### 왜 중요한가?

- 거대한 인터페이스를 여러 클라이언트가 공유하면,
  - **변화에 취약한 의존성**이 생긴다.
  - **불필요한 구현**을 강요받는다.
- 이는 OCP(Open-Closed Principle) 위반으로 이어질 수 있다.

---

### SRP(단일 책임 원칙)과의 관계

- **SRP**: 클래스의 변경 이유를 하나로 제한
- **ISP**: 클라이언트가 사용하는 기능만 인터페이스로 노출

> 둘 다 **역할 단위로 책임을 분리하자**는 공통 철학을 지닌다.  
> 실제로 SRP 위반을 해결하다 보면 ISP를 함께 적용하는 경우가 많다.

---

### ISP 위반 예시

```java
public interface MultiFunctionPrinter {
    void print(Document doc);
    void scan(Document doc);
    void fax(Document doc);
}
```
