### Q1. Ceiling of a number-
![[Drawing 2025-09-09 02.06.05.excalidraw | 600]]
#### **Ans-**
![[Drawing 2025-09-09 03.22.11.excalidraw | 570]]



### Q2. Floor of a number-
![[Drawing 2025-09-09 03.38.59.excalidraw | 600]]
#### **Ans-**
![[Drawing 2025-09-09 03.43.26.excalidraw | 570]]

### Q3. [Find Smallest Letter Greater Than Target](https://leetcode.com/problems/find-smallest-letter-greater-than-target/)
![[Drawing 2025-09-11 03.26.00.excalidraw | 700]]

#### **Ans-**
![[Drawing 2025-09-11 03.43.40.excalidraw | 600]]
##### **Code-**
```java
package BinarySearch;  
  
public class CeilingOfLetter {  
    public static void main(String[] args) {  
        char[] letters = { 'c', 'f', 'j' };  
        System.out.println(nextGreatestLetter(letters, 'd'));  
    }  
    
    
    static char nextGreatestLetter(char[] letters, char target) {  
        int start = 0;  
        int end = letters.length - 1;  
		  
        while(start <= end) {  
            int mid = start + (end - start) / 2;  
            
            if (target < letters[mid]) {  
                end = mid - 1;  
                
            } else if (target > letters[mid]) {  
                start = mid + 1;  
                
            }  
            
            // the wrap around condition  
            if (target > letters[letters.length - 1]) return letters[0];  
            
            
        }     
        
        return letters[start];  
    }
}
```

### Q4. [Find First and Last Position of Element in Sorted Array](https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array/)
![[Drawing 2025-09-13 02.23.15.excalidraw | 600]]
#### **Ans-**
![[Drawing 2025-09-13 02.28.58.excalidraw | 620]]

##### **Code-**
```java
package BinarySearch;  
  
import java.util.Arrays;  
  
public class FirstAndLast {  
    public static void main(String[] args) {  
        int[] arr = { 1 , 3 , 4 , 5 , 5 , 5 , 5 , 7 , 7 , 7 , 14 };  
		  
        System.out.println(Arrays.toString(searchRange(arr, 5)));  
    }  
	
    static int[] searchRange(int[] nums, int target) {  
        int[] ans = {-1 , -1};  
		  
        //check for first occurrence of target first  
		  
        int start = search(nums, target, true);  
        int end = search(nums, target, false);  
		  
        ans[0] = start;  
        ans[1] = end;  
        return ans;  
    }  
	  
	  
    //function to return the index of target  
    static int search(int[] nums, int target, boolean findStartIndex){  
		  
        int ans = -1;  
        
        // just normal binary search from here
        int start = 0;  
        int end = nums.length - 1;  
		  
        while(start <= end){  
            int mid = start + (end - start) / 2;  
            if (target < nums[mid]){  
                end = mid - 1;  
            } else if (target > nums[mid]) {  
                start = mid + 1;  
            } else {  
                // potential ans  
                ans = mid;  
				  
                if (findStartIndex){  
                    end = mid - 1;  
                } else {  
                    start = mid + 1;  
                }  
            }  
			  
        }  
		  
        return ans;  
    }  
}
```

### Q5. [Searching in an Infinite Sorted Array](https://www.geeksforgeeks.org/dsa/find-position-element-sorted-array-infinite-numbers/)
![[Drawing 2025-09-17 01.46.32.excalidraw | 600]]
#### **Ans-**
![[Drawing 2025-09-17 01.49.16.excalidraw  | 600]]
![[Drawing 2025-09-17 02.23.19.excalidraw | 400]]
##### **Code-**
```java
package BinarySearch;  
  
public class SearchingInInfiniteArray {  
    public static void main(String[] args) {  
        int[] arr = { 3, 3, 4, 5, 6, 8, 9, 14, 17, 26, 36, 47 };  
        int target = 5;  
        System.out.println(ans(arr , target));  
    }  
	  
	
    static int ans(int[] arr, int target){  
        //First we will find the range  
        //Starting with box of two  
        int start = 0;  
        int end = 1;  
		  
        while (target > arr[end]){  
            //target won't be in the size of chunk we have rn  
            //double the size of the chunk            int newStart = end + 1;  
            end = end + (end - start + 1)*2;  
            start = newStart;  
			  
        }  
		  
        return binarySearch(arr, target, start, end);  
    }  
	  
    static int binarySearch(int[] arr, int target, int start, int end){  
        while(start <= end){  
            int mid = start + (end - start) / 2;  
            // mid is essentially the average, but it's written this way  
            // to not exceed the integer limit (2147483647) if in case the array is huge  
            if (target < arr[mid]){  
                end = mid - 1;  
            } else if (target > arr[mid]) {  
                start = mid + 1;  
            } else {  
                // ans  
                return mid;  
            }  
		  
        }  
        // if target is not found in the array then just return -1  
        return -1;  
		  
    }  
}
```

### Q6. [Peak Index in a Mountain Array](https://leetcode.com/problems/peak-index-in-a-mountain-array/)

#### **Ans-**
![[Drawing 2025-09-17 03.29.16.excalidraw | 560]]





[[Binary Search]]