# COMPUTER 2013
## Q1

(a) **Precedence of operators** means the order in which operators are evaluated in an expression.

(b) A **literal** is a fixed value directly written in the code, such as `10`, `'A'`, or `3.14`.

(c) 
| Concept Description                                                                 | Java Concept     |
|-------------------------------------------------------------------------------------|------------------|
| (i) A superclass and a subclass                                                     | Inheritance      |
| (ii) Representing essential features without background details                     | Abstraction      |

## Q2

(b)  
| Statement      | Description                                                                 |
|----------------|-----------------------------------------------------------------------------|
| `break`        | Exits the loop immediately.                                                 |
| `continue`     | Skips the current iteration and continues with the next loop iteration.    |

## Q2

(c)  
```java
char[] arr = {'a', 'b', 'c'};
int len1 = arr.length;          // For character array
String str = "abc";
int len2 = str.length();        // For String object
```

## Q3

(a)  
```java
digital mp4 = new digital();
```

(b)  
```java
String s1 = "good";
String s2 = "world matters";
String str1 = s2.substring(5).replace('t', 'n'); // " matters" -> " manners"
String str2 = s1.concat(str1); // "good manners"
```

| Variable | Value          |
|----------|----------------|
| str1     | " manners" → " manners" with 't' → 'n' = " manners" |
| str2     | "good manners" |

(f)  
| Function                 | Return Type |
|--------------------------|-------------|
| isWhitespace(char ch)    | boolean     |
| Math.random()            | double      |

(g)  
```java
ut + 0.5 * f * Math.pow(t, 2)
```

(j)  
| Task                                       | Scanner Method    |
|-------------------------------------------|-------------------|
| (i) Input an integer data                 | `nextInt()`       |
| (ii) Input a String data (single word)    | `next()`          |
|      Input a String data (entire line)    | `nextLine()`      |

## Q5

```java
import java.util.Scanner;

public class ISBNCheck {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter 10-digit ISBN: ");
        String isbn = sc.next();

        if (isbn.length() != 10) {
            System.out.println("Illegal ISBN");
            return;
        }

        int sum = 0;
        for (int i = 0; i < 10; i++) {
            char ch = isbn.charAt(i);
            if (!Character.isDigit(ch)) {
                System.out.println("Illegal ISBN");
                return;
            }
            int digit = Character.getNumericValue(ch);
            sum += (i + 1) * digit;
        }

        if (sum % 11 == 0)
            System.out.println("Legal ISBN");
        else
            System.out.println("Illegal ISBN");
    }
}
``` 

## Q9

```java
import java.util.Scanner;

public class MenuProgram {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("1. Check Composite Number");
        System.out.println("2. Find Smallest Digit");
        System.out.print("Enter your choice: ");
        int choice = sc.nextInt();

        switch (choice) {
            case 1:
                System.out.print("Enter a number: ");
                int num = sc.nextInt();
                boolean isComposite = false;
                if (num > 3) {
                    for (int i = 2; i <= num / 2; i++) {
                        if (num % i == 0) {
                            isComposite = true;
                            break;
                        }
                    }
                }
                if (isComposite)
                    System.out.println("Composite Number");
                else
                    System.out.println("Not a Composite Number");
                break;

            case 2:
                System.out.print("Enter an integer: ");
                int n = sc.nextInt();
                n = Math.abs(n);
                int smallest = 9;
                while (n > 0) {
                    int d = n % 10;
                    if (d < smallest)
                        smallest = d;
                    n /= 10;
                }
                System.out.println("Smallest digit is " + smallest);
                break;

            default:
                System.out.println("Invalid choice");
        }
    }
}
``` 
