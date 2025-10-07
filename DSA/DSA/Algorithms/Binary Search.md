- As we learned in the linear search it was nothing but a for loop which iterated over every element in the array till it found the element needed. Whose time complexity of O(n).
- In Binary Search the array has to be a **Sorted** Array, in that we first find the middle element in the array and then see if the target element is less than or greater than the target element.
- Now if we know that if the target element is greater/less than or equal to the middle element and if the array is already a sorted array then we already know that the target element will lie on the right/left of the element. After that we change the start and end depending on the greater and less and again take the middle.
- We keep checking if the middle is > or < or == to the target till it comes equal to target element.
- If start become greater than the target (start > target) then the element doesn't exist in the array.
- This approach decreases the time complexity of searching by a lot.
- ![[Drawing 2025-09-08 01.58.25.excalidraw]]
- This algo will have Time Complexity of O(logN)
  ![[Drawing 2025-09-09 01.22.28.excalidraw]]![[Drawing 2025-09-09 01.33.53.excalidraw | 570]]


#### **If we know that the array is sorted in ascending order-**

```java
package BinarySearch;  
  
public class BinarySearch {  
    public static void main(String[] args) {  
        int[] arr = {2, 3, 4, 5, 12, 34, 55, 64, 78};  
        System.out.println(binarySearch(arr, 55));  
    }  
    
    static int binarySearch(int[] arr, int target){  
        int start = 0;  
        int end = arr.length - 1;  
        
        while(start <= end){  
	        
            int max = Integer.MAX_VALUE;  
            int mid = start + (end - start) / 2;  
            // mid is essentially the average, but it's written this way  
            // to not exceed the integer limit (2147483647) if in case the array is really big  
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

#### **If we do not know that the array is sorted in either ascending or descending order-**
```java
package BinarySearch;  
  
public class OrderAgnosticBS {  
    public static void main(String[] args) {  
        int[] arr = {23, 22, 12, 8, 6, 3, 2, -2, -5, -6};  
        System.out.println(orderAgnosticBS(arr, 3));  
    }  
    
    static int orderAgnosticBS(int[] arr, int target){  
        int start = 0;  
        int end = arr.length - 1;  
		  
        boolean isAsc = arr[start] < arr[end];  
		  
        while(start <= end){  
            int max = Integer.MAX_VALUE;  
            int mid = start + (end - start) / 2;  
            // mid is essentially the average, but it's written this way  
            // to not exceed the integer limit (2147483647) if in case the array is huge  
            
            if (arr[mid] == target){  
                return mid;  
            }  
            
            if (isAsc){  
                if (target < arr[mid]){  
                    end = mid - 1;  
                } else {  
                    start = mid + 1;  
                }            
            } else {  
                if (target > arr[mid]){  
                    end = mid - 1;  
                } else {  
                    start = mid + 1;  
                }           
             }  
             
             
        }        
        // if target is not found in the array then just return -1  
        return -1;  
    }
    
}
```


## [[Binary Search Questions]]-
![[Binary Search Questions]]
[[Data Structures and Algorithms]]