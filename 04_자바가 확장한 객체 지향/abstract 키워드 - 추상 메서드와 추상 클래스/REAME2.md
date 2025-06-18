# 면접 질문 내용

## 1. 추상 클래스 (Abstract Class)

- **키워드:** `abstract`
- **특징:**
  - 인스턴스 생성 불가
  - 추상 메서드와 일반 메서드 모두 가질 수 있음
  - 상속을 통해 자식 클래스에서 추상 메서드 구현 필요

- **예시 코드:**
  ```java
  public abstract class Animal {
      public abstract void makeSound();
      public void eat() {
          System.out.println("Eating...");
      }
  }
  ```

 ## 2. 인터페이스 (Interface)

역할:
클래스가 구현해야 하는 메서드 목록을 정의 (계약)
다형성 구현 가능
다중 구현 가능 (다중 상속 대체)
특징 (Java 8 이후 기준):
기본 메서드 (default) 정의 가능
정적 메서드 (static) 정의 가능
여전히 상태(state)는 가질 수 없음 (상수 제외)
예시 코드:
  ```java
public interface Flyable {
    void fly();
}

public class Bird implements Flyable {
    public void fly() {
        System.out.println("Bird is flying");
    }
}

  ```

## 3. 제네릭 (Generics)

사용 목적:
타입 안정성 보장 (컴파일 타임 타입 체크)
불필요한 형변환 제거
코드 재사용성 증가
자주 사용하는 제네릭 타입:
List<T>
Map<K, V>
Optional<T>
예시 코드:

  ```java
List<String> names = new ArrayList<>();
names.add("Alice");
String first = names.get(0); // 캐스팅 필요 없음

public class Box<T extends Number> {
    private T value;
}


  ```

