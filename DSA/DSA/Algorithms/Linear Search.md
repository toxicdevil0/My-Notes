Linear is a simple search algorithm in array done to find a certain element in it.
It is a simple for loop iterating for all the elements in the array to find the element required.
It's time complexity will be therefore of O(N) [where N denotes the no. elements in the array].

```java
public class Main {  
    public static void main(String[] args) {  
        int[] nums = {32, 43, 43, 42, 12, 4};  
        System.out.println(linearSearch(nums, 4));  
    }  
    
    static int linearSearch(int[] arr, int target){  
        if (arr.length == 0){  
            return -1;  
        }  
        
        for (int i = 0; i <arr.length ; i++) {  
            if(arr[i] == target){  
                return i;  
            }        
        }
        // if target doesn't exist in the given array  
        return -1;  
    }
}
```

*str==.toCharArray()== (where str is a string) is a method which can be used to make an Array of all the characters in the string.*

## Searching in a 2D Array
It's quite similar to that of a simple array, where instead of iterating in a array only, we search for the every single row or column and as we already know, 2D array actually look like this
![[Drawing 2025-08-22 02.03.14.excalidraw | 500]]
we are just iterating in the individual arrays inside the array

it's code looks something like this-
```java
import java.util.Arrays;  
  
public class SearchIn2DArray {  
    public static void main(String[] args) {  
        int[][] nums = {  
                {23, 34},  
                {43, 23, 12, 13},  
                {32, 43, 12}  
        };  
        System.out.println(Arrays.toString(linearSearch(nums, 34)));  
    }    
    
    static int[] linearSearch(int[][] arr, int target){  
        for (int row = 0; row <arr.length ; row++) {  
            for (int column = 0; column <arr[row].length ; column++) {  
                if(arr[row][column] == target){  
                    return new int[]{row, column};  
                }            
	        }           
        }  
              
        //if not found  
        return new int[] {-1, -1};  
    }
}
```

## Leetcode Questions

### Q1. [Find Numbers with Even Number of Digits](https://leetcode.com/problems/find-numbers-with-even-number-of-digits/)

**My Answer**-
*THINKING- Change Every element to a string and then check how many digits are there in the string as every input in that array is an integer and we can find the no. of digits using **.length()** of string. and then check if it's even by diving by 2 and if it's divisible by 2 then increase the sum.*
```java
package LinearSearch;  
//https://leetcode.com/problems/find-numbers-with-even-number-of-digits/submissions/1743692604/  
public class EvenDigitsLinearSearch {  
    public static void main(String[] args) {  
        int[] arr = {12,345,2,6,7896};  
        
        System.out.println(findNumbers(arr));  
    }  
    
    static int findNumbers(int[] nums){  
        int sum = 0;  
        for (int num : nums) {  
            if ((Integer.toString(num).length()) % 2 == 0) {  
                sum++;  
            }        
        }
        return sum;  
    }
    
}
```

**OR**

We can find the number of digits of the integer by-
while the integer / 10 is not equal to 0
	increase count
if count at the end is even then increase sum
```java
static int findNumbers2(int[] nums){  
    int sum = 0;  
    for (int num : nums) {  
        int count = 0;  
        while (num != 0) {  
            num /= 10;  
            count++;  
        }  
        if (count % 2 == 0) {  
            sum++;  
        }    
    }    
    return sum;  
}
```

**OR** (the most interesting one)

To get the number of digits in any integer we can use
```java
Math.log10(num)
```
so if the num is lets is 232434
then it will give 6

### Q2. [Richest Customer Wealth](https://leetcode.com/problems/richest-customer-wealth/)
**My Answer-**
*It's just a simple question where you just have to iterate in a 2D Array*
```java
package LinearSearch;  
//https://leetcode.com/problems/richest-customer-wealth/description/
public class RichestCustomerWealth {  
    public static void main(String[] args) {  
        int[][] arr = {{1,2,3},{3,2,1}};  
  
        System.out.println(maximumWealth(arr));  
    }    
    static int maximumWealth(int[][] accounts) {  
        int max = Integer.MIN_VALUE;  
        for (int[] account : accounts) {  
            int sum = 0;  
            
            for (int wealth : account) {  
                sum += wealth;  
            }            
            
            if(sum > max){  
                max = sum;  
            }        
        }        
    return max;  
    }
}
```
---
[[Data Structures and Algorithms]]