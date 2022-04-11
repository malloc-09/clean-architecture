### LSP

>부모 타입의 참조 변수를 사용하여 구현된 코드에서, 그 참조 변수에 자식 타입 객체를 대입해도, 아무 문제 없이 잘 작동해야 한다.

LSP가 위배되면 별도 매커니즘을 추가해야함

#### 아키텍쳐에서의 LSP  
LSP는 인터페이스와 구현체에도 적용되는 광범위한 소프트웨어 설계 원칙  
인터페이스를 구현하는 클래스, 동일한 REST 인터페이스에 응답하는 서비스 집단 등



#### 위반 사례
1. Square / Rectangle
```
public class Rectangle {
    double width;
    double height;
    public void setWidth(double width) {
        this.width = width;
    }
    public void setHeight(double height) {
        this.height = height;
    }
    public double getArea() { 
        return width * height;
    }
}

public class Square extends Rectangle {
    @Override
    public void setWidth(double width) {
        this.height = width;
        this.width = width;
    }
    @Override
    public void setHeight(double height) {
        this.height = height;
        this.width = height;
    }
}

=> square에서의 setWidth,setHeight 동작이 달라짐
```
2. REST - 택시 파견 서비스
```
/driver/{name}
/pickupAddress/{Address}
/pickupTime/{time}
/destination/{destination}

acme.com
/driver/{name}
/pickupAddress/{Address}
/pickupTime/{time}
/dest/{destination}

=> acme를 위한 별도의 처리가 필요해짐
```