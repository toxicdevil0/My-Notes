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
[[Java]]
