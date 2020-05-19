# Object 

* class와 instance 기본   
   class는 연관된 method를 grouping해서 이름을 붙인 것.   
   
   instance는 class를 바탕으로 실체화 한것.    
   실체화 된 instance는 메모리에 할당 됨.

```
    import java.io.FileWriter;
    import java.io.IOException;
     
    public class OthersOOP {
     
        public static void main(String[] args) throws IOException {   
            
            // class : System, Math, FileWriter
            // instance : f1, f2
             
            System.out.println(Math.PI);
            System.out.println(Math.floor(1.8));
            System.out.println(Math.ceil(1.8));
             
            FileWriter f1 = new FileWriter("data.txt");
            f1.write("Hello");
            f1.write(" Java");
             
             
            FileWriter f2 = new FileWriter("data2.txt");
            f2.write("Hello");
            f2.write(" Java2");
            f2.close();
             
            f1.write("!!!");
            f1.close();
        }
     
    }
```

* 변수와 method   
 ````
class Print{
    public static String delimiter = "";   //class 소속의 변수를 만들어서 다른 메소드에서 변수를 사용가능 하게 함.
    public static void A() {
        System.out.println(delimiter);
        System.out.println("A");
        System.out.println("A");
    }
    public static void B() {
        System.out.println(delimiter);
        System.out.println("B");
        System.out.println("B");
    }
}
public class MyOOP {
    public static void main(String[] args) {
        Print.delimiter = "----";
        Print.A();
        Print.B();
        
        Print.delimiter = "****";
        Print.A();
        Print.B();
    } 
````

* class의 형식   
````
//class라는 키워드로 Print라는 class 생성
class Print {   
    public static String delimiter = "";      //class의 member(변수,method) : A, B, deliimiter
 
    public static void A() {
        System.out.println(delimiter);
        System.out.println("A");
        System.out.println("A");
    }
 
    public static void B() {
        System.out.println(delimiter);
        System.out.println("B");
        System.out.println("B");
    }
}

public class MyOOP {
    public static void main(String[] args) {
        Print.delimiter = "----";
        Print.A();
        Print.A();
        Print.B();
        Print.B();
 
        Print.delimiter = "****";
        Print.A();
        Print.A();
        Print.B();
        Print.B();
    }
}
````
 
 * instance 의 기본개념   
        -원형 class를 복제 한 것.  
        -여러 상태의 class가 동시에 필요할 때 사용.    
        -new 키워드 이용해서 instance 이름 설정 (*ex)Print p1 = new Print();  
        -class 파일의 method에 static을 없앰.   
        
````
public class MyOOP {
        public static void main(String[] args) {
            Print p1 = new Print();   // new를 사용하여 p1이라는 class의 instance 생성
            p1.delimiter = "----";
            p1.A();
            p1.A();
            p1.B();
            p1.B();
     
            Print p2 = new Print();   //new를 사용하여 p2라는 class의 instance 생성
            p2.delimiter = "****";
            p2.A();
            p2.A();
            p2.B();
            p2.B();
             
             
            p1.A();
            p2.A();
            p1.A();
            p2.A();
        }
````
````class Print {
        public String delimiter = "";
     
        //mehtod에서 static을 지움.
        public void A() {
            System.out.println(delimiter);
            System.out.println("A");
            System.out.println("A");
        }
     
        public void B() {
            System.out.println(delimiter);
            System.out.println("B");
            System.out.println("B");
        }
