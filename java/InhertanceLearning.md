#상속

##상속

* 상속은 이미 개발된 클래스를 재사용해서 새로운 클래스를 만들기 때문에 중복되는 코드를 줄여준다.     
 상속을 이용하면 부모 클래스의 수정으로 모든 자식 클래스들도 수정되는 효과를 가져오기 때문에 유지 보수 시간을 최소화할 수도 있다.      
 
 * 클래스 상속   
 -프로그램에서는 자식이 부모를 선택한다. 자식 클래스를 선언할 때 어떤 부모 클래스를 상속받을 것인지 결정하고, 다음과 같이 기술한다.
 
 ````
class 자식클래스 extends 부모클래스 {
//필드
//생성자
//메소드
}
````

* 상속의 특징    
    * 여러개의 부모클래스를 상속할 수 없다. extends 뒤에는 단 하나의 부모 클래스만 와야 한다.
    * 부모 클래스에서 private 접근 제한을 갖는 필드와 메소드는 상속 대상에서 제외된다.     
    부모와 자식 클래스가 다른 패키지에 존재한다면 default 접근 제한을 갖는 필드와 메소드도 상속 대상에서 제외된다.      

* 부모 생성자 호출     
-자식 객체를 생성하면 부모 객체가 먼저 생성되고 자식 객체가 생성 된다.      
-모든 객체는 클래스의 생성자를 호출해야만 생성된다. 부모 생성자는 자식 생성자의 맨 첫 줄에서 호출된다.     
-생성자가 명시적으로 선언되지 않았다면 컴파일러가 super(); 라는 기본 생성자를 생성한다.
-자식 생성자를 직접 선언하고 명시적으로 부모 생성자를 호출하고 싶을 때.
````
자식클래스( 매개변수선언, ...) {
    super( 매개값,...);
    ...
}
````

-super()가 생략되면 컴파일러에의해 자동적으로 추가되기 때문에 부모의 기본 생성자가 존재해야한다.    
부모의 기본생성자가 없고 매개 변수가 있는 생성자만 있다면 자식 생성자에서 부모 생성자 호출을 위해 super( 매개값,...)
를 명시적으로 호출해야 한다. super(매개값,...)는 반드시 자식 생성자 첫 줄에 위치해야 하며, 그렇지 않으면 컴파일 에러가 발생한다.

* 메소드 재정의   
 -메소드 재정의는 자식 클래스에서 부모 클래스의 메소드를 다시 정의하는 것을 말한다. 다음과 같은 규칙에 주의해서 작성해야 한다.
    * 부모의 메소드와 동일한 시그니처(리턴타입, 메소드 이름, 매개 변수 목록)를 가져야 한다.
    * 접근 제한을 더 강하게 재정의 할 수 없다.
    * 새로운 예외를 throws 할 수 없다.    
    * 메소드가 재정의되었다면 부모 객체의 메소드는 숨겨지기 때문에, 자식 객체에서 메소드를 호출하면 재정의된 자식 메소드가 호출된다.       

* 부모 메소드 호출     
 -자식 클래스에서 부모 클래스의 메소드를 재정의하게 되면, 부모 클래스의 메소드는 숨겨지고 재정의된 자식 메소드만 사용된다.      
 그러나 자식 클래스 내부에서 재정의된 부모클래스의 메소드를 호출해야 하는 상황이 발생하면 명시적으로 super 키워드를 붙여 부모메소드를 호출 할 수 있다.
 ````
super.부모메소드();
````
 
 ## 타입 변환과 다형성
 
 * 자동 타입 변환     
 -자동 타입 변환은 프로그램 실행 도중에 자동적으로 타입 변환이 일어나는 것을 말한다.       
 -자동 타입 변환의 개념은 자식은 부모의 특징과 기능을 상속받기 때문에 부모와 동일하게 취급될 수 있다는 것이다.        
 예를 들어, 고양이가 동물의 특징과 기능을 상속 받았다면 '고양이는 동물이다'가 성립하는 것.
 ````
Cat cat = new cat();   
Animal animal = cat;
//Animal animal = new Cat(); 도 가능
````

-위 코드에서 cat과 animal 변수는 타입만 다를뿐 동일한 Cat 객체를 참조.      
두 변수를 ==연산 해보면 true가 나오는데, 두 변수가 동일한 객체를 참조하고 있다는 뜻.    
바로 위의 부모가 아니더라고 상속 계층에서 상위 타입이라면 자동 타입 변환이 일어날 수 있다.       
    
-부모 타입으로 자동 타입 변환된 이후에는 부모 클래스에 선언된 필드와 메소드만 접근이 가능하다.      
변수는 자식 객체를 참조하지만 변수로 접근 가능한 멤버는 부모 클래스 멤버로만 한정된다.       
그러나 메소드가 자식 클래스에서 재정의 되었다면 자식 클래스의 메소드가 대신 호출된다.        
        
* 필드의 다형성       
-다형성을 구현하기 위해서 자동 타입 변환을 사용한다.        
-필드의 타입을 부모 타입으로 선언하면 다양한 자식 객체들이 저장될 수 있기 때문에 필드 사용 결과가 달라질 수 있다.      
        
* 매개 변수의 다형성        
-자동 타입 변환은 주로 메소드를 호출 할 때 많이 발생한다.      
-메소드를 호출할 때에는  매개 변수 타입과 동일한 매개값을 지정하는 것이 정석이지만, 매개값을 다양화하기 위해 매개 변수에 자식 객체를 지정할 수도 있다.     
        
       
 * 강제 타입 변환
 -강제 타입 변환은 부모 타입을 자식 타입으로 변환하는 것을 말한다.
 ````
Parent parent = new Child();     //자동 타입 변환
Child child = (Child) parent;    //강제 타입 변환
````

-자식 타입이 부모 타입으로 자동 변환하면, 부모에 선언된 필드와 메소드만 사용 가능한 제약이 따른다.   
만약 자식에 선언된 필드와 메소드를 사용해야 할때 강제 타입 변환을 해서 자식 타입을 변환한 다음 사용하면 된다.

* 객체 타입 확인      
-강제 타입 변환은 자식 타입이 부모 타입으로 변환되어 있는 경우에만 사용 가능하다.     
부모 변수가 참조하는 객체가 부모 객체인지 자식 객체인지 확인할 때 instanceof 연산자를 사용한다.     
    
    -instanceof 연산자의 좌항에는 객체가 오고 우항에는 타입이 오는데, 좌항의 객체가 우항의 인스턴스이면 true, 아니면 false를 리턴
    ````
  boolean result = 좌항(객체) instanceof 우항(타입)
  ````
        
   -instanceof 연산자는 주로 매개값의 타입을 조사할 때 사용된다. 메소드 내에서 강제 타입 변환이 일어날 경우 확인 후 안전하게 강제 타입 변환을 해야 한다.
   ````
  public void method(Parent parent) {
  if(parent instanceof Child) {  //parent 매개 변수가 참조하는 객체가 Child인지 조사
  Child child = (Child) parent;
    }
  }
  ````
  -강제 타입 변환을 하기 전에 객체 타입조사를 하지 않으면 예외가 발생할 수 있다. 예외가 발생하면 프로그램은 즉시 종료되기 때문에 객체 타입 조사가 필요하다.