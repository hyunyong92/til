# 변수와 타입

##변수 
* 변수(variable)는 값을 저장할 수 있는 메로리의 특정 번지에 붙이는 이름      
* 자바에서의 변수는 다양한 타입의 값을 저장할 수 없다. ex)정수 타입 변수 -> 정수값, 실수 타입 변수 -> 실수값    
1. 변수 선언    
-변수를 사용하기 위해서는 먼저 변수를 선언해야 한다. 변수 선언은 변수에 어떤 타입(type)의 데이터를 저장할 것인지와 변수 이름이 무엇인지를 결정한다.
```
int age;     //정수를 저장할 수 있는 int 타입 age 변수 선언
double score; //실수형을  저장할 수 있는 double 타입 score 변수 선언
int a, b, c; //같은 타입의 변수는 콤마(,)를 이용해서 한꺼번에 선언할 수도 있다.
```
* 변수 이름의 규칙     
    
작성규칙|예
----|----
첫 번째 글자는 문자이거나 '$','_'이어야 하고 숫자로 시작할 수 없다.| 가능:price,$price,_price
영어 대소문자를 구분한다| firstname과 firstName은 다른 변수
첫 문자는 영어 소문자로 시작하되, 다른 단어가 붙을 경우 첫 문자를 대문자로 한다.(관례)|maxSpeed, firstName
문자 수의 길이 제한은 없다|
자바 예약어는 사용할 수 없다|

2\. 값 저장    
-변수에 값을 저장할 때에는 대입 연산자(=)를 사용한다. 수학에서는 등호의 의미지만 자바에서는 오른쪽의 값을 왼쪽 변수에 저장한다는 의미를 가진다.     
````
int score;      //변수 선언
score = 90;     //값 저장
````
-변수를 선언 했다고 하더라도 변수에 값이 저장되지 않으면 변수가 생성되지 않는다.  
변수에 최초로 값이 저장 될 때 변수가 생성되는데 이것을 변수 초기화 라고 하고 이때 저장 되는 값 초기값 이라 한다.
````
int value;                  //변수 선언
int result = value + 10;    //value의 값이 초기화 되지 않았기 때문에 컴파일 에러 발생
---
int value = 30;             //value 변수가 30으로 초기화 됨
int result = value + 10;    //value 값을 읽고 10을 더해 result에 저장
````
3\. 변수의 사용 범위       
-자바의 모든 변수는 중괄호 {} 블록 내에서 선언되고 사용된다. 메소드 블록 내에 선언된 변수를 지역변수(local varialbe)이라고 하는데, 메소드 실행이 끝나면 메모리에서 자동으로 사라진다.    
-변수는 블록 내 어디에서든 선언할 수 있지만, 변수 사용은 자신이 속한 블록 내부에서만 사용할 수 있다.     
* 변수 선언시 주의 사항  
-변수가 어떤 범위에서 사용될 것인지 생각하고, 선언 위치를 결정해야 한다.      
-메소드 블록 전체에서 사용하고 싶다면 메소드 블록 첫머리에 선언한다.     
-특정 블록 내부에서만 사용된다면 해당 블록 내에 선언한다.

