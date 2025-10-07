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

[[Java]]
