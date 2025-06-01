## ✅ 예제 코드

```java
public class Start3 {

    public static void main(String[] args) {
        int i = 10;
        int k = 20;

        if (i == 10) {
            int m = k + 5;
            k = m;
        } else {
            int p = k + 10;
            k = p;
        }
    }
}
```

## 💡 주요 포인트

- `if 블록 안의 지역 변수`는 해당 블록이 끝나면 메모리에서 사라진다.
- `블록 구조마다 독립적인 스택 프레임`이 존재할 수 있다.
- **조건문 분기**는 프로그램 실행 흐름과 메모리 상태에 영향을 준다.
- `STS 에서는` 제어문의 스택 프레임까지 보여주지 않음.
- `if 블록 스택 프에임이` 존재한다는 사실을 꼭 기억
