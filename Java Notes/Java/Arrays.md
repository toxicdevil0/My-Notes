
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

[[Java]]
