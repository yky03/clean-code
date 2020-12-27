
### 함수

- 작게 만들어라  
: 한 화면에서 보일 정도로만, 최대한 적은 라인으로 중첩문의 위치나 이름이 의미있는 역할을 할 수 있도록 한다.  

- 한 가지만 해라  
: 의미 있는 이름이 한가지만 나오는지 검토해보면 정답이 있다.  

- 함수당 추상화 수준은 하나로  
: 코드를 위에서 아래로 이야기처럼 읽을 수 있어야 좋다.  
(내려가기 규칙으로써 위에서 아래로 프로그램을 읽으면 함수 추상화 수준이 한번에 한단계씩 낮아진다.)  

- Switch문  
: 작게 만들자, 다형성을 이용하여 중복코드 및 OCP(Open Closed Principle, 새 유형을 추가할때마다 코드를 변경해야 하는 구조)를 제거하자.  

```
//Before (함수가 길다, 한가지 작업만 수행하지 않는다, SRP(Single Responsibillity Principle)를 위반한다, OCP를 위반한다.)  
//isPayday, deliverPay 등의 스위치 함수 등이 계속 추가될 수 있다.  
public Money caculatePay(Employee e) throws InvalidEmployee{
 switch(e.type){
  case COMMISSIONED:
   return calculateCommissionedPay(e);
  case HOURLY:
   return calculateHourlyPay(e);
  case SALARIED:
   return calculateSalariedPay(e);
  default:
   throw new InvalidEmployeeType(e.type);
```

```
//After 추상팩토리에 꽁꽁 숨긴다. 스위치문 딱 한번은 참아준다.  
Public abstract class Employee{
 public abstract boolean isPayday();
 public abstract Money calculatePay();
 public abstract void deliverPay(Money pay);
}
//
public interface EmployeeFactory{
 public Employee makeEmployee(EmployeeRecord r) throws InvalidEmployeeType;
}
//
public class EmployeeFactoryImpl implements EmployeeFactory{
 public Employee makeEmployee(EmployeeRecord r) throws InvalidEmployeeType{
  switch(r.type){
   case COMMISSIONED:
    return new CommissionedEmployee(r);
   case HOURLY:
    return new HourlyEmployee(r);
   case SALARIED:
    return new SalariedEmployee(r);
   default:
    throw new InvalidEmployeeType(r.type);
    }
   }
 }
```
- 서술적인 이름을 사용하라  
: 여러 단어가 쉽게 읽히는 명명법을 사용한다. 일관성이 있어야 한다. 함수명만 보고도 다른 함수 혹은 추가될 함수명 까지도 짐작할 수 있도록.   

- 함수 인수
: 함수의 이상적인 인수 개수는 0개이다, 다음은 1개, 다음은 2개, 다음부터는 피하는것이 좋다.  
테스트 관점에서 보면 인수의 조합이 늘어날수록 테스트도 어려워진다.  
플래그인수, 이항 함수도 피할것.  

- 부수 효과를 일으키지 마라  
: 함수에서 한가지를 하겠다고 약속하고 다른 일을 끼워넣지 말아라.  

- 오류 코드 보다는 예외를 사용하라  
: 함수명 == OK -> try catch  

- 반복하지 마라  
: include 방법으로 중복을 없애던지 다른 방법을 사용해라.  

- 구조적 프로그래밍  
: 함수에는 return 문이 하나여야 한다.(루프 안에서 break, continue는 사용하지말고 goto도 작은 함수에서는 지양해라)  

* 결론 함수는 어떻게 자야할까  
: 생각을 먼저 정리한 후 다듬기, 단위 테스트 케이스를 만들고 코드를 다듬고, 함수를 만들고, 이름을 바꾸고, 중복을 제거하거, 메서드를 줄이고 등... 계속해서 다듬는다.  






