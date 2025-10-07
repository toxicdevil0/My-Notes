1. Class is a blueprint which defines some properties and behaviors. An object is an instance of a class which has those properties and behaviors attached.
2. A class is not allocated memory when it is defines. An object is allocated memory when it is created.
3. Class is a logical entity whereas objects are physical entities.
4. A class is declared only once. On the other hand, we can create multiple objects of a class
5. A class is a way to arrange data and behavior information. It is a template that must be implemented by its objects.
6. A class can also be seen as a user defined data type where any object of defined data type has some predefined properties and behaviors.

*Class's names should always start with a capital letter.*
**Classes are stored in metaspace in Java.**


```java
package Classes;  
  
public class classobject {  
    public static void main(String[] args) {  
		  
        Dog d1 = new Dog();  
        Dog d2 = new Dog();  
        d1.name = "Tommy";  
        d2.name = "Kalu";  
        
        d1.bark();  
        
        d2.walk();  
          
    }  
    
}  
class Dog{  
    String name;  
    int age;  
	
    void bark(){  
		
        System.out.println(name+" is barking");  
    }  
		
    void walk(){  
        System.out.println(name+" wants to go on a walk :> ");  
    }  
	
}
```


### Inheritance-
In java to inherit properties from other class we use keyword `extends`.

```java
package Classes;  
  
public class Car {  
	  
    int wheelsCount;  
		
    void start(){  
        System.out.println("Car is starting");  
    }  
}
```
```java
package Classes;  
  
public class Vehicle extends Car {  
    public static void main(String[] args) {  
        Car obj = new Car();  
		
        obj.wheelsCount = 4;  
		
        obj.start();  
        System.out.println(obj.wheelsCount);  
    }  
	  
}
```


### Encapsulation
Encapsulation means to make some things private or locked in the code.
It is done by using access modifiers. There are 3 types of access modifiers-
1. `public`
2. `private`
3. `protected`

#### static keyword
If we want to access class members without creating an instance of the class, we need to declare the class members static.

Static variables can be accessed by calling the class name of the class. There is no need to create an instance of the class for accessing the static variables because static variables are the class variables and are shared among all the class instances.

##### static variables
- only a single copy of the static variable is created and shared among all the instances of the class.
- because it is a class-level variable, memory allocation of such variables only happens once when the class is loaded in the memory.
- if an object modifies the value of static variable, the change is reflected across all objects.
- Static variable can be used in any type of method: static or non-static.
- non-static variables cannot be used inside static methods. it will throw compile-time error.

#### static block
static block gets executed when class is getting executed before anything else gets executed.

---
[[Java]]
