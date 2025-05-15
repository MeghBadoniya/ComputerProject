# Computer Project  
# 2011 Paper  

## Q1  

### Difference between Object and Class (2 Marks)

| Class                            | Object                               |
|----------------------------------|---------------------------------------|
| A class is a blueprint or template for creating objects. | An object is an instance of a class. |
| It defines properties and behaviors (methods) but does not occupy memory. | It has state and behavior and occupies memory. |

### What does the 'token' keyword refer to? (2 Marks)

A **token** in Java refers to the smallest individual unit in a program. Tokens include keywords, identifiers, literals, operators, and separators.

### Example:
```java
int number = 10;
```

### Difference between Entry Controlled Loop and Exit Controlled Loop (2 Marks)

| Entry Controlled Loop                       | Exit Controlled Loop                        |
|---------------------------------------------|---------------------------------------------|
| Condition is checked before entering the loop body. | Condition is checked after executing the loop body. |
| Loop body may not execute if the condition is false. | Loop body executes at least once regardless of the condition. |

### Difference between '/' and '%' Operator (2 Marks)

| '/' Operator                          | '%' Operator                           |
|-------------------------------------|--------------------------------------|
| Performs division and gives the quotient (result without remainder). | Performs division and gives the remainder. |
| Example: `10 / 3` results in `3`.   | Example: `10 % 3` results in `1`.    |

## Q2

### Total Size of an Array (2 Marks)

- If `arr[4]` is a **char** array:  
  Each `char` is 2 bytes in Java.  
  Total size = 4 × 2 = **8 bytes**

- If `arr[4]` is a **float** array:  
  Each `float` is 4 bytes in Java.  
  Total size = 4 × 4 = **16 bytes**

### Package Containing Scanner Class (2 Marks)

The `Scanner` class is contained in the package:

```java
java.util;
```

## Unit of Class Called When Object is Created (2 Marks)

The **constructor** of a class is called when an object of the class is created.

## Output of the Given Code (2 Marks)

```java
String n = "Computer Knowledge.";
String m = "Computer Applications";

System.out.println(n.substring(0, 8).concat(m.substring(9)));
System.out.println(n.endsWith("e"));
```

```text
ComputerApplications
false
```

## Q3

### (d) Output (2 Marks)

```java
System.out.println(Character.isUpperCase('R'));
System.out.println(Character.toUpperCase('j'));
```

```text
true
J
```

### (e) Role of keyword void in declaring functions (2 Marks)

```java
// 'void' indicates the method returns no value.
void exampleMethod() {
    // method body
}
```

### (a) Loop execution and output analysis (3 Marks)

```java
int p = 200;
int t = 0;
while(true) {
    if(p < 100)
        break;
    p = p - 20;
    t++;
}
System.out.println(p);
```

Output:
```text
80
```

### (b) Output of given code (3 Marks)

(i)
```java
int k = 5, j = 9;
k += ++j + k;
System.out.println("k=" + k);
System.out.println("j=" + j);
```

Output:
```text
k=24
j=10
```

(ii)
```java
double b = -15.6;
double a = Math.rint(Math.abs(b));
System.out.println("a=" + a);
```

Output:
```text
a=16.0
```

### (c) Constructor Overloading with Example (3 Marks)

```java
class Example {
    int x;

    Example() { // Default constructor
        x = 0;
    }

    Example(int a) { // Parameterized constructor
        x = a;
    }
}
```

### (d) Prototype of function search (2 Marks)

```java
int search(String sentnc, String wrd);
```

### (e) Expression in Java (2 Marks)

```java
z = x + y / (5 * x * 3) + 2 * y;
```

### (f) Statements on String (2 Marks)

(i) Find and display position of last space in string `s`:

```java
System.out.println(s.lastIndexOf(' '));
```

(ii) Convert string variable `x` to double:

```java
double d = Double.parseDouble(x);
```

### (g) Keyword that informs error in I/O operation (2 Marks)

```java
throws
```

### What are Library Classes? (2 Marks)

Library classes are pre-written classes provided by Java that programmers can use to perform common tasks without writing code from scratch.

### Example:
```java
import java.util.Scanner;

Scanner input = new Scanner(System.in);
```

## Q6  
### Program to check Special Number (Using main function only)

```java
import java.util.Scanner;

public class SpecialNumber {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter a number: ");
        int num = sc.nextInt();
        int temp = num, sum = 0;

        while (temp > 0) {
            int digit = temp % 10;
            int fact = 1;
            for (int i = 1; i <= digit; i++) {
                fact *= i;
            }
            sum += fact;
            temp /= 10;
        }

        if (sum == num)
            System.out.println(num + " is a special number.");
        else
            System.out.println(num + " is not a special number.");
    }
}
```

## Q9  
### Menu driven program for:

- (a) Print series 0, 3, 7, 15, 24 ... n terms  
- (b) Find sum of series S = 1/2 + 3/4 + 5/6 + ... + 19/20  

```java
import java.util.Scanner;

public class SeriesMenu {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.println("Menu:");
        System.out.println("1. Print series 0, 3, 7, 15, 24 ... n terms");
        System.out.println("2. Find sum of series 1/2 + 3/4 + 5/6 + ... + 19/20");
        System.out.print("Enter your choice (1 or 2): ");
        int choice = sc.nextInt();

        switch(choice) {
            case 1:
                System.out.print("Enter number of terms (n): ");
                int n = sc.nextInt();
                int val = 0;
                for (int i = 0; i < n; i++) {
                    System.out.print(val + " ");
                    if (i == 0)
                        val = 3;
                    else
                        val = val + i + 3;
                }
                System.out.println();
                break;

            case 2:
                double sum = 0.0;
                for (int i = 1; i <= 19; i += 2) {
                    sum += (double) i / (i + 1);
                }
                System.out.printf("Sum of series = %.2f\n", sum);
                break;

            default:
                System.out.println("Invalid choice.");
        }
    }
}
```