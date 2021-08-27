## BigDecimal

> Java.math 안에 있는 클래스로 **정확한 숫자계산**을 위한 클래스이다.
돈과 소수점을 다루는 중요한 프로그램에 쓰인다.

### 부동 소수점 방식의 오차

실수 연산에서는 소수점 단위 값을 정확히 표현하는 것이 아니라 근사값으로 처리하기 때문에 오차가 발생할 수 있다.

### BigDecimal은 다음과 같이 선언한다.

>BigDecimal money = new BigDecimal(“10000.12345”);

인자 값이 `string`이므로 숫자로 쓰고싶을 경우에는 형 변환을 해주어야 한다.

>BigDecimal.valueof(10000.12345)

처럼 `valueof`를 사용한다면 `double`형으로 바꾸어 사용할 수 있다.

**사칙연산**은 `.add()`, `.subtract()`, `.divide()`, `.multiply()`, `.remainder()`로 가능하다.

