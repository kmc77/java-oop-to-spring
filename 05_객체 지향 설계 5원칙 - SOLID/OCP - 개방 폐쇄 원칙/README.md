## OCP - 개방 폐쇄 원칙

*소프트웨어 엔터티(클래스, 모듈, 함수 등)는 확장에 대해서는 열려 있어야 하지만 변경에 대해서는 닫혀 있어야 한다. - 로버트 c.마틴*<br>
*자신의 확장에는 열려 있고, 주변의 변화에 대해서는 닫혀 있어야 한다.*

<p align="center">
<img src="https://github.com/kmc77/java-oop-to-spring/blob/main/05_%EA%B0%9D%EC%B2%B4%20%EC%A7%80%ED%96%A5%20%EC%84%A4%EA%B3%84%205%EC%9B%90%EC%B9%99%20-%20SOLID/OCP%20-%20%EA%B0%9C%EB%B0%A9%20%ED%8F%90%EC%87%84%20%EC%9B%90%EC%B9%99/IMG_4804.jpg" width="600"/>
  <sub><i>개방 폐쇄 원칙 O</i></sub>
</p>

오라클은 MySql 이나 MS-Sql로 교체할 때 자바 애플리케이션은 JDBC 인터페이스라고 하는 완충 장치로 인해 변화에 영향을 받지 않는다. 바로 자바 애플리케이션은 DB라고 하는 주변의 변화에 닫혀 있는 것이다.
DB를 교체한다는 것은 DB가 자신의 확장에 열려 있다는 것이다.

### 스프링 프레임워크
- 개방 폐쇄 원칙을 교과서적으로 활용하고 있다.
