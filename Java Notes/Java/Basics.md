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
[[Java]]
