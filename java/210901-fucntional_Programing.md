## 람다식

> 함수형 프로그래밍에서 쓰이는 방식을 칭한다.
익명함수로 쓰이며 `(매개변수) -> {실행문;}`의 형식으로 사용된다.

```
Ex) int add(int x, int y){
   Return x+y;
}
```

위와 같은 메서드가

```
(int x, int y) -> {return x+y;}
```
로 간결해진다.

**코드가 간결해지는 장점이 있으나, 가독성이 떨어지는 단점이 있다.**

## 함수형 인터페이스

> 람다식을 선언하기 위한 인터페이스이다.
익명 함수와 매개 변수만으로 구현되므로 인터페이스는 **단 하나의 메서드만을 선언해야한다.**
`@FunctionalInterface` 어노테이션이 쓰이며 함수형 인터페이스라는 의미를 가진다.

```
Ex)
@FunctionalInterface
public interface MyNumber {

    int getMax(int num1, int num2);
}
```



