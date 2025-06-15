## 어댑터 패턴 (Adapter Pattern)

### 정의
- 서로 다른 인터페이스를 가진 클래스들을 연결해주는 중간 역할.
- 클라이언트는 기대한 인터페이스를 통해 호출하지만, 실제 구현은 다른 클래스를 사용하는 방식.

### 예시 코드 (Java)
```java
// 호환되지 않는 기존 클래스
class OldPrinter {
    void printOld(String message) {
        System.out.println("Old Printer: " + message);
    }
}

// 기대하는 인터페이스
interface Printer {
    void print(String message);
}

// 어댑터 클래스
class PrinterAdapter implements Printer {
    private OldPrinter oldPrinter;

    public PrinterAdapter(OldPrinter oldPrinter) {
        this.oldPrinter = oldPrinter;
    }

    @Override
    public void print(String message) {
        oldPrinter.printOld(message);
    }
}
```

### 스프링 프레임워크 적용 예시
- HandlerAdapter (Spring MVC 내부 구성 요소)<br>
    다양한 형태의 컨트롤러(@Controller, HttpRequestHandler, @RestController)를 공통된 방식으로 실행<br>
    DispatcherServlet → HandlerAdapter → 실제 핸들러 호출
