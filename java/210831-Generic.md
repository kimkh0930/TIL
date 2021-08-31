## Generic 프로그래밍

> 클래스에서 사용하는 변수의 자료형이 여러 개이나 기능이 동일한 경우 클래스의 자료형을 특정하지 않고 해당 클래스를 사용할 때 지정할 수 있도록 선언하는 방식이다.
실제 사용되는 자료형의 변환은 컴파일러에 의해 검증되어 안정적이다.

### 다이아몬드 연산자 <>

> Generic의 타입을 넣어주는 부분으로 `generic<> a = new generic<>();` 의 형식으로 사용한다. 
앞의 다이아몬드 연산자에 타입을 넣어준다면 **뒤쪽에는 넣어줄 필요가 없다.**

### T extends

>Generic type에서 상속이 가능하다 `generic<T exteds material>`의 형식으로 사용하며 T에 무작위 클래스가 들어갈 수 없도록 형식을 지정하는 역할을 한다.
위의 `Material`은 임의로 지정한 **상위 클래스**이며 `powder, plastic`등의 **하위 클래스**가 **상속**받는다고 가정할 수 있다. 
상위 클래스는 직접 사용되지 않기 때문에 `abstract` 클래스로 지정하는 경우가 많다.

### Generic 메서드

> 자료형 매개 변수가 하나 이상인 경우도 있다.
**Generic 클래스가 아니어도 내부에 generic 메서드는 구현 가능하다.**
`Public <자료형 매개 변수> 반환형 메서드 이름(자료형 매개변수…){}`의 형식으로 사용한다.

Ex)
* 두 점을 기준으로 사각형을 만들 때 사각형의 너비를 구하는 메서드가 있다. 
* 두 점이 정수인지 실수인지 모르기 때문에 제네릭 타입을 사용하는 예시이다.

```
public class GenericMethod {

    public static<T,V> double makeRectangel(Point<T,V> p1,Point<T,V> p2){

        double left = ((Number)p1.getX()).doubleValue();
        double right = ((Number)p2.getX()).doubleValue();
        double top = ((Number)p1.getY()).doubleValue();
        double bottom = ((Number)p2.getY()).doubleValue();

        double width = right - left;
        double height = bottom - top;

        return width * height;
    }

    public static void main(String[] args) {

        Point<Integer, Double> p1 = new Point<>(0,0.0);
        Point<Integer, Double> p2 = new Point<>(10,10.0);

        double size = GenericMethod.<Integer, Double>makeRectangel(p1,p2);
        System.out.println(size);
    }
}
```

