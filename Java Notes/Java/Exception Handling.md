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
[[Java]]
