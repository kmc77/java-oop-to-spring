## 프록시 패턴 (Proxy Pattern)

### 정의
- 다른 객체에 대한 접근을 제어하는 대리 객체를 제공
- 실제 객체 대신 프록시를 통해 기능을 확장하거나, 로깅/보안/트랜잭션 등을 처리


### 예시 코드 (Java)
```java

// 공통 인터페이스
interface Service {
    void operation();
}

// 실제 서비스 객체
class RealService implements Service {
    public void operation() {
        System.out.println("실제 서비스 실행");
    }
}

// 프록시 객체
class ServiceProxy implements Service {
    private RealService realService;

    public ServiceProxy(RealService realService) {
        this.realService = realService;
    }

    public void operation() {
        System.out.println("접근 제어 시작");
        realService.operation();
        System.out.println("로깅/후처리 종료");
    }
}
```

### 스프링 프레임워크 적용 예시
- AOP (Aspect-Oriented Programming)
  - @Transactional, @Async, @Cacheable 등은 프록시 기반으로 동작
  - ProxyFactoryBean, BeanPostProcessor, JDK 동적 프록시, CGLIB 등 활용
