### ISP
>클라이언트는 자신이 사용하지 않는 인터페이스에 의존하지 않아야
한다.

ISP가 위배되면 사용하지 않는 인터페이스에 의존성이 생기게되고, 이로 인해 사용하지 않는 코드로 인한 수정이 생김.

* ISP는 언어의 종류에 따라 영향받는 정도가 달라짐. 동적 타입 언어는 재컴파일, 재배포가 필요 없음

#### ISP와 아키텍쳐
소스코드와 동일하게 컴포넌트간 의존성에서도 발생 가능

### 위반 사례
```
class OPS{
    public void method1(){...};
    public void method2(){...};
}
class User1{
    ...
    pulbic void method(){
        OPS ops= new OPS();
        ops.method1();
    }
}
class User2{
    ...
    pulbic void method(){
        OPS ops= new OPS();
        ops.method2();
    }
}
```