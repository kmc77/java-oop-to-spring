# 오늘 대답 부족했던 주제 정리

---

## 1. ✅ Java Interface의 목적

### "인터페이스를 왜 쓰는가?" 에 대한 답변이 부족했음

### 정리:

- **구현체 교체 유연성**: 코드를 바꾸지 않고 구현만 바꾸는 유연함 제공
- **다형성 활용**: 다양한 객체를 같은 인터페이스 타입으로 처리 가능
- **OCP(개방-폐쇄 원칙)** 만족: 기능을 확장하되 기존 코드는 수정하지 않음
- **DI(의존성 주입)** 기반 설계 가능 → 테스트 용이성 향상

---

## HTTP vs HTTPS

| 항목        | HTTP                       | HTTPS                          |
|-------------|----------------------------|--------------------------------|
| 보안        | 없음                        | SSL/TLS로 암호화됨              |
| 포트        | 80                         | 443                             |
| 사용처      | 내부망 등                   | 로그인, 결제 등 민감한 정보 전달 |
| 주요 기능   | 평문 전송                   | 대칭키 + 비대칭키 암호화         |

---

## Spring Boot 특징

- **내장 Tomcat**: 별도 WAS 필요 없음
- **의존성 관리**: `starter`로 자동 관리
- **설정 최소화**: `application.yml` or `.properties`
- **빠른 실행**: 배포형 JAR 생성으로 바로 실행 가능
- **자동 설정**: `@SpringBootApplication` → @ComponentScan + @EnableAutoConfiguration 등 포함

---

## JWT vs OAuth2 vs Spring Security

### JWT
- **Stateless 인증 방식**
- Payload 안에 사용자 정보 포함 (Base64 인코딩)
- Access + Refresh Token 구조

### OAuth2
- **3rd-party 인증 (소셜 로그인 등)**
- Authorization Code → Access Token 발급
- 인증 주체는 Google, Naver 등 외부

### Spring Security
- 인증/인가 필터 체인 제공 (`FilterChainProxy`)
- `Authentication`, `Authorization`, `SecurityContext` 관리
- JWT나 OAuth2와 통합 가능

---

## 인증(Authentication) vs 인가(Authorization)

| 구분       | 인증 (Authentication)           | 인가 (Authorization)           |
|------------|----------------------------------|----------------------------------|
| 개념       | "누구냐" → 본인 확인               | "허용된 기능이냐" → 권한 확인       |
| 처리위치   | 로그인 시 처리                     | 요청 시 권한 체크 (예: `@PreAuthorize`) |
| 예시       | ID/PW 확인, JWT 토큰 검증         | 관리자만 접근 가능한 API 제한        |

---

## 📝 회원가입 시 처리한 값

- 이메일 (중복 체크)
- 비밀번호 (BCrypt 암호화 저장)
- 닉네임
- 권한(Role): 기본 USER
- 가입 일자(LocalDateTime)
- 소셜로그인 여부 (Provider)

---

## WAS vs WS 차이

| 구분    | WAS (Web Application Server) | WS (Web Server)             |
|---------|-------------------------------|-----------------------------|
| 역할    | 동적 컨텐츠 처리 (JSP, Servlet) | 정적 파일 처리 (HTML, CSS)   |
| 예시    | Tomcat, Jetty                 | Nginx, Apache               |
| 특징    | Java 기반 비즈니스 로직 처리    | 클라이언트 요청 라우팅/캐싱    |

---

## Bcrypt 암호화 비교 방법

- 단방향 해시 (복호화 불가)
- `matches(rawPw, encodedPw)` 메서드로 비교
- 내부적으로 **salt**가 추가되어 동일한 입력도 다른 해시값 생성

```java
BCryptPasswordEncoder encoder = new BCryptPasswordEncoder();
encoder.matches("입력비번", "DB에 저장된 해시값");
