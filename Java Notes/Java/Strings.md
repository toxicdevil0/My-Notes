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
[[Java]]
