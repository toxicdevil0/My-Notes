There are two types of memory:
1. Stack Memory(ordered memory)
2. Heap Memory(unordered memory) 


### Java Object Class
Object class is present in java.lang package. Every class in Java is directly or indirectly derived from object class. It's the top most class  in Java.


###### .toString() of object class
all the Strings are stored in the different as strings are used alot in java.
and whenever they are called, they get called using the .toString method
```java
package ObjectClass;  
  
  
class CarModel{  
    String model;  
	  
    int year;  
	  
    public CarModel(String model, int year){  
        this.model = model;  
        this.year = year;  
		  
		  
    }  
    
@Override  
    public String toString(){  
        return "Car's Model "+model+"and year is "+year;  
    }  
}  
  
  
public class LearnObjectClass {  
    public static void main(String[] args) {  
        CarModel obj = new CarModel("Honda", 2020);  
		  
        System.out.println(obj.toString());  
    }  
}
```

in here `toString()` method is getting overridden from the object class.
and we can remove `.toString` and it will give the same output.
```java
public class LearnObjectClass {  
    public static void main(String[] args) {  
        CarModel obj = new CarModel("Honda", 2020);  
		  
        System.out.println(obj);  
    }  
}
```


##### .equals() method
`.equals()` in Strings method checks if the Strings is equal or not.
AND it is not limited to String.
```java
package ObjectClass;  
  
  
class CarModel {  
    String model;  
	  
    int year;  
	  
    public CarModel(String model, int year) {  
        this.model = model;  
        this.year = year;  
		  
		  
    }   
}  
  
  
public class LearnObjectClass {  
    public static void main(String[] args) {  
        CarModel obj1 = new CarModel("Honda", 2020);  
        CarModel obj2 = new CarModel("Honda", 2020);  
        System.out.println(obj1.equals(obj2));  
        System.out.println(obj1);  
        System.out.println(obj2);  
    }  
}
```

*OUTPUT*-
```
false
ObjectClass.CarModel@8efb846
ObjectClass.CarModel@2a84aee7
```

```java
package ObjectClass;  
  
  
class CarModel {  
    String model;  
	  
    int year;  
	  
    public CarModel(String model, int year) {  
        this.model = model;  
        this.year = year;  
		  
		  
    }  
      
    @Override  
    public boolean equals(Object obj){  
        CarModel that = (CarModel)obj;  
        if(this.model.equals(that.model) && this.year == that.year){  
            return true;  
            
        }  
        return false;  
		  
    }  
	
	  
}  
  
public class LearnObjectClass {  
    public static void main(String[] args) {  
        CarModel obj1 = new CarModel("Honda", 2020); 
        CarModel obj2 = new CarModel("Honda", 2020);  
		  
        System.out.println(obj1.equals(obj2));  
        System.out.println(obj1);  
        System.out.println(obj2);  
    }  
}
```
here we Override the `.equals()` method
and the output gives true.
*OUTPUT*-
```
true
ObjectClass.CarModel@8efb846
ObjectClass.CarModel@2a84aee7
```

##### .hashCode()
`.hashCode` generates an identity int that is different for different objects.

### How to change String '2' to Integer 2

```java
int digit = num.charAt(i) - '0;
```
- **`num.charAt(i)` gives you a character, like `'2'`.**
    
- **In Java, characters are stored as ASCII/Unicode values.**
    
    - **`'0'` has a value of 48**
        
    - **`'1'` is 49**
        
    - **`'2'` is 50, and so on.**
        
- **So `'2' - '0'` becomes:**  
    **`50 - 48 = 2` ✅**
    
**This works for all digits `'0'` to `'9'`**



---
[[Java]]
