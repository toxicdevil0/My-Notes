 Java is written in a specific Java environment, JVM
same operators and relational ops as C++
to print we do it in main class and then put `System.out.println();`

## [[Basics]]
### To take user input
in order to use the object of Scanner, we need to import `java.util.Scanner`
```java
Scanner sc = new Scanner(System.in)
float num = sc.nextFloat();
```

```java
import java.util.Scanner;

public class UserInput {
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		System.out.println("Enter your age:");
		int age = sc.nextInt();
		System.out.println("Your age is "+age);
	}
}
```

### How to change the datatype explicitly
```java
int firstNumber = 45;
long secondNumber = 5565433957384;
int result = (int)(firstNumber + secondNumber);
```

---

## [[Conditional Statements]]
it's the same as C++ or C
```java
if(pssy == ranthrough){
System.out.println("She's a fucking WHORE.");
} else {
System.out.println("Viable option.)"
}
```

### Larger of three numbers
```java
package Basics;  
  
import java.util.Scanner;  
  
public class conditionalStatements {  
    public static void main(String[] args) {  
        Scanner sc = new Scanner(System.in);  
        System.out.println("Enter first number:");  
        int a = sc.nextInt();  
        System.out.println("Enter second number:");  
        int b = sc.nextInt();  
        System.out.println("Enter third number:");  
        int c = sc.nextInt();  
        
        
        if(a>b){  
            System.out.println("a is bigger than b");  
            if(a>c){  
                System.out.println("a is largest "+a);  
            } else {  
                System.out.println("c is largest "+c);  
            }  
        } else {  
            System.out.println("b is bigger than a");  
        } if(b>c){  
            System.out.println("b is largest " + b);  
        }  
    }  
}
```

after taking 3 numbers from user we check which of the numbers is the greatest
this is the most basic if-else-if statement example

#### Ternary Operator (?)
written in a way 
`condition ? expression1 : expression2;`
if condition is true then expression1 gets executed else expression2 *just like if-else statements but written in a single line*
`max = a>b ? a : b;`
`System.out.println(max)`
if a>b then a gets printed, else b

---

## [[Loops]]
for loops-
```java
package Loops;  
  
import java.util.Scanner;  
  
public class loop {  
    public static void main(String[] args) {  
        Scanner sc = new Scanner(System.in);  
        System.out.println("Enter a number:");  
        int n = sc.nextInt();  
            for(int i = 1; i<=10 ; i++){  
                System.out.println(n+" X "+i+" = "+i*n);  
            }  
    }  
}
```
*OUTPUT*-
```
Enter a number:
7
7 X 1 = 7
7 X 2 = 14
7 X 3 = 21
7 X 4 = 28
7 X 5 = 35
7 X 6 = 42
7 X 7 = 49
7 X 8 = 56
7 X 9 = 63
7 X 10 = 70
```

### Sum of N natural numbers
```java
package Loops;  
  
import java.util.Scanner;  
  
public class loop {  
    public static void main(String[] args) {  
        Scanner sc = new Scanner(System.in);  
        System.out.println("Enter a number:");  
        int n = sc.nextInt();
        int sum = 0;  
            for (int i = 1; i<= n; i++){  
                sum = sum + i;  
            }  
        System.out.println("Sum is: "+sum);  
    }  
}
```
*OUTPUT*-
```
Enter a number:
7
Sum is: 28
```
it gives the sum by looping as
sum = 0 + 1
sum = 1 + 2
so if n = 7
sum will be 1+ 2+ 3+ 4+ 5+ 6+ 7 =28

or for first n even numbers
```java
for (int i = 1; i<= n; i++){  
	sum = sum + 2*i;  
}  
```

### Break and continue
to get out of the loop we use `break;`
to skip a certain step we use `continue;`

### Nested Loops
loop inside another loop
```java
package Loops;  
  
public class nestedLoops {  
    public static void main(String[] args) {  
        for (int i = 0; i <5 ; i++) {  
            for (int j = 0; j <10 ; j++) {  
                System.out.print(j+" ");  
                
            }  
            System.out.println();  
            
        }  
    }  
}
```

#### Patterns-
```java
package Loops;  
  
public class nestedLoops {  
    public static void main(String[] args) {  
        for (int i = 0; i <5 ; i++) {  
            for (int j = 0; j <=i ; j++) {  
                System.out.print(j+" ");  
                
            }  
            System.out.println(); 
             
        }  
    }  
}
```
*OUTPUT*-
```
0 
0 1 
0 1 2 
0 1 2 3 
0 1 2 3 4 
```
the first loop tells how many times the inner loop has to work and the inner loop outputs or prints the pattern needed

now for the star pattern
```java
package Loops;  
  
public class nestedLoops {  
    public static void main(String[] args) {  
        for (int i = 0; i <7 ; i++) {  
            for (int j = 0; j <=i ; j++) {  
                System.out.print("* ");  
                
            }  
            System.out.println();  
        }  
    }  
}
```
*OUTPUT*-
```
* 
* * 
* * * 
* * * * 
* * * * * 
* * * * * * 
* * * * * * * 
```

---


## [[Arrays]]

Arrays are stored in contiguous memory (consecutive memory locations) 
if we are to call some data in an array it find the data stored in the 0-index or the 1st index of that array and then find the data in that array depending on the data-type
let's say there an array 
![[Pasted image 20250707010334.png]]
and we want to access the 4th one in this array, then the system will find the starting of the array and based on the datatype go to index 3. if the 0 index data was stored in memory at a random location of 12232 and if it was `int` data-type then, to go to 4th it will add 4 and 3 time to get to the 4th so the 4th one is stored at (12232 + 4 * 3) 12244 in the memory

`int age[] = new int[5] // allocating memory to array`

Arrays are static in java, i.e. ,the size of arrays can't change after declaring it once.

```java
package Arrays;  

public class array {  
    public static void main(String[] args) {  
        int age[] = new int[5];  
        age[0]= 1;  
        age[1]= 2;  
        
        System.out.println(age[0]);  
        System.out.println(age.length);
    }  
}
```
*OUTPUT*-
```
1
5
```

 You can also directly initialize by writing the array in "{}" brackets.
`int marks[] = {22, 43, 43, 41, 53};`

 to iterate in Arrays we use **for-loops or for each loops**
### Iterating in Array

#### Through For loop-
```java
package Arrays;  
  
public class array {  
    public static void main(String[] args) {  
		
        int marks[] = {22, 43, 43, 41, 53};  
        for (int i = 0; i <marks.length ; i++) {  
            System.out.println("Marks of student "+(i+1)+" = "+marks[i]);  
            
        }  
        
    }  
}
```
*OUTPUT*-
```
Marks of student 1 = 22
Marks of student 2 = 43
Marks of student 3 = 43
Marks of student 4 = 41
Marks of student 5 = 53
```

#### Through For Each Loop
```java
package Arrays;  
  
public class array {  
    public static void main(String[] args) {  
	    
        int marks[] = {22, 43, 43, 41, 53};  
        for (int mark :marks){  
            System.out.println("Marks of each student = "+mark);  
        }  
        
    }  
}
```
*OUTPUT*-
```
Marks of each student = 22
Marks of each student = 43
Marks of each student = 43
Marks of each student = 41
Marks of each student = 53
```

#### To Find Sum of the Elements in an Array-
```java
package Arrays;  
  
public class Sum {  
    public static void main(String[] args) {  
        int numbers[] = {34, 53, 75, 23, 65, 64, 43};  
        
        int sum = 0;  
        
        for (int number: numbers){  
            sum += number;  
        }  
        System.out.println("Sum is "+sum);  
    }  
}
```
*OUTPUT*-
```
Sum is 357
```

#### To Find Smallest or Biggest number in an Array-
```java
package Arrays;  
  
public class min {  
    public static void main(String[] args) {  
        int numbers[] = {34, 53, 75, 23, 65, 64, 43};  
  
        int min = Integer.MAX_VALUE;  
  
        for (int number :numbers){  
            if(number < min){  
                min = number;  
            }  
        }  
  
        int max = Integer.MIN_VALUE;  
  
        for (int number :numbers){  
            if(number > max){  
                max = number;  
            }  
        }  
  
        System.out.println("minimum no. is:"+min);  
        System.out.println("maximum no. is:"+max);  
    }  
}
```
*OUTPUT*-
```
minimum no. is:23
maximum no. is:75
```

### 2-Dimensional Array

```java
package Arrays;  
  
public class twoDimensionalArray {  
    public static void main(String[] args) {  
        int matrix[][] = {  
                {32, 23 ,32},  
                {33, 34, 65},  
                {12, 67, 43}  
        };  
        
        
    }  
}
```

---


## [[Methods]]
A method is a block of code or collection of statements or a set of code grouped together to perform a certain task or operation. It is used to achieve the reusability of code.

Just like C++ Functions (it's more or less the same).

To declare a Method in Java
we do it like this 
### Math Class Methods- 
there are some in-built methods in java

1. `Math.min(x,y)`
2. `Math.max(x,y)`
3. `Math.sqrt(x,y)`
4. `Math.pow(x,y)`
5. `Math.abs(x)` (Math.abs(-3) = 3)
6. `Math.random()`
7. `Math.floor(x)`
8. `Math.ceil(x)`
9. `Math.round(x)`

*Example*-
```java
package Methods;  
  
public class methods {  
    public static void main(String[] args) {  
        System.out.println(getRand());  
        
    }  
    
    public static int getRand(){  
        return (int) (Math.random()*5 + 1);  
    }  
    
}
```


---


## [[Strings]]
In Java, String is basically an object that represents a sequence of char values.
An array of characters works same as Java String.
It is a non-primitive data-type.

##### To create a String-
1. `String name = new String("Anuj");` (new different strings with different memories)
2. `String name = "Anuj";` (if another variable has same string then it will point to the same memory)
3. `String name2 = "Anuj";` (will point to the string of the same memory of name)


**As strings are used alot in java, so as to optimize the string in java, there is a designated space in Heap Memory. And to optimize it, in java if we make some another variable of string which already exists in it then instead making a new string it will point the new variable to the String that already exists.**
![[Pasted image 20250710024452.png]]

*Example*-

```java
package Strings;  
  
public class string {  
    public static void main(String[] args) {  
        String name = "Ritik";  
        String sameName = "Ritik";  
        
        String newName = new String("Ritik");  
        
        System.out.println(name);  
        System.out.println(newName);  
        
        if (name == sameName){  
            System.out.println("Both names are same.");  
        }  
        if (name == newName){  
            System.out.println("Both names are same.");  
        } else {  
            System.out.println("Both names are not same.");  
        }  
    }  
}
```

*OUTPUT*- 
```
Ritik
Ritik
Both names are same.
Both names are not same.
```

- To compare values irrespective of where they are stored  we use equals method using `name.equals(newName)`

### Adding two Strings-
```java
package Strings;  
  
import java.util.Scanner;  
  
public class fullName {  
    public static void main(String[] args) {  
        Scanner sc = new Scanner(System.in);  
        
        System.out.println("Enter your first name:");  
        String firstName = sc.nextLine();  
        
        System.out.println("Enter your last name:");  
        String lastName = sc.nextLine();  
        
        System.out.println("Your full name is: "+firstName+" "+lastName);  
    }  
}
```

*OUTPUT*-
```
Enter your first name:
Ritik
Enter your last name:
Prajapat
Your full name is: Ritik Prajapat
```

### Java String Methods-
1. **`.toUpperCase()`**
2. **`.toLowerCase()`**
3. **`trim()`**
4. **`startsWith()`**
5. **`endsWith()`**
6. **`equals()`**
7. **`equalsIgnoreCase()`**
8. **`charAt()`**
9. **`valueOf()`**
10. **`replace()`**
11. **`contains()`**
12. **`substring()`**
13. **`split()`**
14. **`toCharArray()`**
15. **`isEmpty()`**

##### *Examples-*
1. 
```java
package Strings;  
  
public class stringMethods {  
    public static void main(String[] args) {  
        String name = new String("ritik");  
        String Name = new String("RITIK");  
        String name_ = new String("   sdnak jsadk   ");  
        System.out.println(name.toUpperCase());  
        System.out.println(Name.toLowerCase());  
        System.out.println(name_.trim());  
    }  
}
```
*OUTPUT*-
```
RITIK
ritik
sdnak jsadk
```
2. 
```java
package Strings;  
  
import java.util.Scanner;  
  
public class stringMethods {  
    public static void main(String[] args) {  
        Scanner sc = new Scanner(System.in);  
        
        System.out.println("Cunt".equals("Faggot"));  
        System.out.println("Cunt".equals("Cunt"));  
        System.out.println("Cunt".equalsIgnoreCase("cunt"));  
        System.out.println("huh:");  
        char huh = sc.nextLine().charAt(0);  
        System.out.println(huh);  
        
         
    }  
}
```
*OUTPUT*-
```
false
true
true
huh:
Ritik
R
```
3. 
```java
package Strings;  
  
import java.util.Scanner;  
  
public class stringMethods {  
    public static void main(String[] args) {  
        Scanner sc = new Scanner(System.in);  
          
        int what = 24324;  
        String stringWhat = String.valueOf(what); //this is now a string, therefore no mathematical operations will work on it anymore  
        System.out.println(stringWhat);  
        System.out.println(stringWhat+2); //it won't add 2 as it's now a string  
		
	    
    }  
}
```
*OUTPUT*-
```
24324
243242
```
4. 
```java
package Strings;  
  
import java.util.Scanner;  
  
public class stringMethods {  
    public static void main(String[] args) {  
        
        String retard = "Shane Gillis";  
        String newRetard = retard.replace("Shane", "Donald");  
        System.out.println(retard);  
        System.out.println(newRetard);  
    }  
}
```
*OUTPUT*-
```
Shane Gillis
Donald Gillis
```

---

## [[Classes and Objects]]
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

## [[Abstraction]]
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

## [[Memory]]
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



## [[Polymorphism]]
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


## [[Exception Handling]]
Exception Handling is done so that if there is any runtime error in the code then the code doesn't abruptly stop working at that point.

We write the code that is likely to get some kind of error and put it in `try{ }` block.

And we catch that exception using `catch{ }` block while specifying different types of errors like **ArrayIndexOutOfBounds** e or **ArithmeticException** e(dividing by zero) or we can just use the parent **Exception** e class to catch the exception.

there is also a `finally{ }` block that always runs no matter what.

```java
        try {  
            System.out.println(arr[8]);  
        } catch (ArrayIndexOutOfBoundsException e){  
            System.out.println("Index out of bound");  
        } finally {  
            System.out.println("Hello Retard");  
        }  
```
or
```java
        try {  
            System.out.println(arr[9]);  
        } catch (Exception e){  
            System.out.println("Exception Handled");  
        } finally {  
            System.out.println("Hello Retard");  
        }  
```

Using `Exception e` catches all exceptions, but **you won’t know the specific error** unless you check `e.getClass().getName()` or similar. It's often better to catch specific exceptions when possible.

---

## [[Generic and Wrapper Classes]]
### Wrapper Class-
#### Autoboxing and Unboxing
we can change the datatype of any variable using Integer, Boolean, Float wrapper classes, which is called autoboxing.

some examples of Autoboxing are-
```java
public class Autoboxing {  
    public static void main(String[] args) {  
		  
        Integer obj = Integer.valueOf("23"); // autoboxing  
		  
        Boolean obj2 = Boolean.valueOf("true"); // autoboxing  
		  
        int obj3 = 23; //unboxing  
		  
        String obj4 = String.valueOf(obj3); //autoboxing  
    }  
}
```


## How to change String '2' to Integer 2

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
