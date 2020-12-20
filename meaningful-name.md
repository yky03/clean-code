
## 2. 의미있는 이름

1) 의도를 분명히 밝혀라  
: 의미있는 네이밍 사용할것. ( int a, d ... x )  

2) 그릇된 정보를 피하라  
: 알아보기 쉬운 문자 사용. ( L, O 같은 문자들 주의 )  

3) 의미 있게 구분하라  
: 읽는 사람이 차이를 알도록 이름을 지어라. ( getActivetAccount, getActivetAccounts, getActivetAccountInfo ... x )  

4) 발음하기 쉬운 이름을 사용하라    
: genymdhms, modymdms -> genetationTimeStamp, modificationTimeStamp  

5) 검색하기 쉬운 이름을 사용하라  
: 상수에 이름을 부여, sum 같은 변수 사용.  

6) 인코딩을 피하라  
: 멤버변수 접두어 사용할 필요x IDE를 활용하는 것이 바람직하다.  

7) 자신의 기억력을 자랑하지 마라  
: 변수명을 보고 의미를 파악할 수 있는 명료함이 최고이다.  

8) 클래스 이름  
: 클래스 이름과 객체 이름은 명사나 명사구가 적합하다.  

9) 메서드 이름  
: 메서드 이름은 동사나 동사구가 적합하다.( 접근자, 변경자, 조건자는 javabean 표준에 따라 값 앞에 get, set, is를 붙인다. )  
```
Complex fulcrumPoint = new Complex(23.0);  
-> // 메서드는 아래처럼 인수를 설명하는 이름을 사용하는 것이 더 좋다.  
Complex fulcrumePoint = Complex.FromRealNumber(23.0);  
```  

10) 기발한 이름은 피하라  
: 재미난 이름보다 명료한 이름을 선택하라.( whack() -> kill() )  

11) 한 개념에 한 단어를 사용하라  
: 추상적인 개념 하나에 단어 하나를 선택해 이를 고수한다.  
-> 주석을 뒤져보지 않고도 프로그래머가 올바른 메서드를 선택할 수 있도록 해야한다.(fetch, retrieve, get 제각각 x 일관성 있게 사용)  

12) 말장난을 하지 마라  
: 한 단어를 두 가지 목적으로 사용하지 마라.  

13) 해법 영역에서 가져온 이름을 사용하라  
: JobQueue, Visitor..  

14) 문제 영역에서 가져온 이름을 사용하라  
: 전문가에게 의미를 물어 파악할 수 있다.  

15) 의미 있는 맥락을 추가하라  
: addrFirstName, addrLastName, addrState or address class 생성  

16) 불필요한 맥락을 없애라  
: 모든 클래스에 접두사를 붙이는것은 바람직하지 못함(IDE 자동완성이나, 모듈화 생각)  


결과적으로 누군가 반대할지라도 끊임없이 가독성을 높이는 작업을 하는 리팩토링을 해야 한다!  










