Polymorphism allows us to perform a single action in different ways. The word "poly" means many and "morphs" means forms, So it means many forms. 
There are two types of Polymorphisms
- Compile-time Polymorphism
- Runtime Polymorphism

Method Overriding is **runtime polymorphism**, like how we overrode .equals method from the object class on java.

Method Overloading is compile-time polymorphism

```java
package Basics;  
  
class ParentData{  
  
    public void printdata(int data){  
		  
        System.out.println("The data is "+data);  
    }  
	  
    public void printdata(){  
        System.out.println("Sike no data for you child");  
    }  
	  
      
}  
class Data extends ParentData{  
      
    @Override  
    public void printdata(int data) {  
        System.out.println("Overridden data is " + data);  
    }  
      
    @Override  
    public void printdata(){  
        System.out.println("No data to override.");  
    }  
}  
  
public class TrendyNumber{  
    public static void main(String[] args) {  
        ParentData d;  
		  
        d = new Data();  
        d.printdata();  
		  
        ParentData r = new ParentData();  
        r.printdata();  
    }  
}
```
*OUTPUT*-
```
No data to override.
Sike no data for you child
```
**Here we overriding the method in child class counts as runtime polymorphism
While we overloading .printdata() by defining it for different arguments counts as compile-time polymorphism.**

---
[[Java]]
