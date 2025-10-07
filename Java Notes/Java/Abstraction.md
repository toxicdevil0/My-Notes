Abstraction in OOP allows us to hide the unnecessary details and only show the needed information.
This allows us to manage complexity by omitting or hiding details with a simpler, higher-level idea.
We achieve abstraction by making abstract class. Like how in C++ we made virtual classes.

*We can't make objects in abstract class.*-
![[Pasted image 20250717023047.png]]

```java
public class LearnAbstract {  
    public static void main(String[] args) {  
//        Vehicle v1 = new Vehicle();  
		  
        Car c1 = new Car();  
        c1.accelerate();  
        c1.brake();  
    }  
}  
  
abstract class Vehicle{  
	  
    abstract void accelerate();  
	  
    abstract void brake();  
}  
  
class Car extends Vehicle{  
  
    @Override  
     void accelerate() {  
	  
    }  
	  
    @Override  
     void brake() {  
	 
    }  
}
```

*@Override is used to show that, this function is being overridden from different class.*

Abstraction in java can also be achieved by using "**Interfaces**".
### Interfaces- 
Interfaces are used to achieve abstraction in java, and instead of using `extends` we use `implements`.
##### Advantages- 
-  Interfaces are also used to achieve multiple inheritance in Java.
```java
interface Line{
...
}

interface Polygon{
...
}

class Rectangle implements Line, Polygon{

}
```





```java
package Abstraction;  
  
public class Interface {  
    public static void main(String[] args) {  
		  
        Friend f1 = new Friend();  
		  
        f1.cat();  
        f1.cute();  
        f1.purr();  
		  
    }  
      
}  
  
interface Pet{  
	  
    void cute();  
}  
  
interface Animal{  
	  
    void cat();  
}  
  
interface Cat{  
	  
    void purr();  
}  
  
class Friend implements Pet, Animal, Cat {  
	  
	  
    @Override  
    public void cat(){  
        System.out.println("I have a cat");  
    }  
	  
    @Override  
    public void cute() {  
        System.out.println("My cat is really cute");  
    }  
	  
    @Override  
    public void purr() {  
        System.out.println("My cat purrs");  
    }  
}
```

### Anonymous Class-
A class containing another class also known as nested class. It's possible to create a nested class in java without giving any name.
A nested class that doesn't have any name is known as an anonymous class.
```java
package Abstraction;  
  
public class LearnAnonymous {  
	  
    class Innerclass extends Outerclass{  
	  
    }  
	  
    Outerclass obj = new Outerclass(){  
        void sing(){  
		  
        }  
		  
        public void outerMethod(){  
		  
        }  
    };  
	  
	  
}  
  
class Outerclass{  
	  
    public void outerMethod(){  
	  
    }  
}
```
 so Innerclass and obj are objectively doing the same work.

### Functional Interface
An Interface that contains exactly one abstract method is known as a functional interface.

```java
@FunctionalInterface
interface Sample{
	//abstract method
	int calculate(int val);
}
```


### Lambda Expression
With the help of Functional Interface we can make Lambda Expression.
They are used to define or make objects of class outside without even using new and directly give body of code to the interface in the code. Using `() ->` we can give body or return statement.

![[Pasted image 20250717042000.png]]

```java
package Abstraction;  
  
public class Lambda {  
    public static void main(String[] args) {  
        SuperInterface obj = (int overcooked) -> {  
			  
            System.out.println("The Meat is Overcooked");  
			  
        };  
		  
        obj.grill(3);  
		  
		  
    }  
}  
  
interface SuperInterface {  
	  
    void grill(int overcooked);  
}
```

---
[[Java]]
