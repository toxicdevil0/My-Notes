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

[[Java]]
