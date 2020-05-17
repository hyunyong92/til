## String클래스의 method

- 문자열 길이
    * str이 참조하는 문자열의 길이를 int타입으로 return 해주는 method.
 
    
    * String str = "Hello";
        str.length();  
    
 - 문자열 붙이기 (concat)
    * concat - str이 참조하는 문자열에 인자로 들어온 문자열을 합쳐서 String 타입으로 return하는 method
       
       String 클래스는 불변클래스로 method가 실행되면 새로운 문자열을 만들기 때문에 str의 값은 변하지 않음. 
   
   
    * String str = new Stirng("hello");
 
        System.out.println(str.concat("wolrd")); //출력 결과 hello world
        
        System.out.println(str) // 출력 결과는 hello.
        
- 문자열 자르기 (substring)
     * substring - 한 문자열에서 지정한 범위에 포함된 문자열을 찾음.
     
        str.substring(int start, int end);  **index의 시작은 0번째부터 이고 end 위치에 있는 index는 반환 되지 않음.
        
        
    * String str = "HelloWolrd";
        String str1 = str.substring(5); //5번쨰 index부터 문자열 끝까지. 출력결과 = "Wolrd"
        String str2 = str.substring(0,5); //0번째 index부터 end번째 index의 앞 문자까지. 출력결과 = "Hello"

- 문자열 포함 검사 (contains)
    * contains - 지정된 문자열이 포함되어 있는지 검사.
    
       
    * String str = "containsTest";
        boolean a = "Test" // true를 return.
        
- 문자열 비교 (equals)
    
    
    * String str = "Hello";
        boolean a = str.equals("Hello");  // true를 return
        boolean b = str.equals("World");  // false를 return

- 문자 교체 (replace)
        
    
    * String str = "hello";
        str.replace("ll", "LL");  // 출력결과 = "heLLo"
        
- 문자 반환(charAt)
    * 지정된 index에 있는 문자를 반환
    
    
    *String str = "hello";
        str.charAt(0);   // "h"
      
    
