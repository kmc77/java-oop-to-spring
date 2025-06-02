## Java의 Call by Value 메커니즘 정리

> Java의 Call by Value 방식과 동작 원리를 정리

---

## 핵심 개념

### Call by Value란?

- Java는 **Call by Value** 방식으로 매개변수를 전달합니다.
- 메서드 호출 시, **실제 값의 복사본**이 전달됩니다.
- **원본 값은 변경되지 않습니다.**

---

## 코드 예시

### 1. `square` 메서드 예시

```java
public class CallByValueExample {
    public static void square(int k) {
        k = k * k;  // 지역 변수 k만 변경됨
        System.out.println("메서드 내부 k: " + k);
    }

    public static void main(String[] args) {
        int k = 5;
        System.out.println("호출 전 k: " + k);
        square(k);
        System.out.println("호출 후 k: " + k);
    }
}
```

### 기억해야 할 것들

- **원시 타입** (`int`, `char`, `boolean` 등): 값 자체가 복사됨  
- **참조 타입** (객체, 배열): **참조값(주소)** 이 복사됨  
- 메서드 내부에서 값을 변경해도 **원본에는 영향 없음**

---

### 주의사항

- Java에서는 **Call by Reference는 존재하지 않음**
- 객체의 경우에도 **참조값이 복사**되지만, 여전히 **Call by Value**
- 메서드 내부에서 매개변수 변경 시, **원본 객체 자체는 바뀌지 않음**

---

## 관련 개념

- **Stack Memory**: 지역 변수와 매개변수가 저장되는 공간  
- **Heap Memory**: 객체 인스턴스가 저장되는 공간  
- **Parameter Passing**: 매개변수 전달 방식  
