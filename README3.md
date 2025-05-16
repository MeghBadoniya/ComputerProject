## Q1

(a)  
| Option       | Valid Comment | Reason                              |
|--------------|---------------|-------------------------------------|
| (i) /* comment */     | Yes           | Proper block comment              |
| (ii) /* comment        | No            | Missing closing `*/`             |
| (iii) // comment       | Yes           | Valid single-line comment        |
| (iv) */ comment */     | No            | Starts with `*/`, not allowed    |

(b)  
A **package** is a group of related classes and interfaces.  
Two Java API packages:
- `java.util`
- `java.io`

(c)  
| Description                                                      | Data Type |
|------------------------------------------------------------------|-----------|
| (i) 64-bit integer                                               | `long`    |
| (ii) 16-bit Unicode character with default `'\u0000'`            | `char`    |

(d)  
| float                   | double                  |
|-------------------------|-------------------------|
| 32-bit precision        | 64-bit precision        |

## Q2


(a)  
Order from higher to lower precedence:
1. `++`
2. `%`
3. `>=`
4. `&&`

(b)  
| Statement                              | Type               |
|----------------------------------------|--------------------|
| (i) System.out.println("Java");        | Method invocation  |
| (ii) costPrice = 457.50;               | Assignment         |
| (iii) Car hybrid = new Car();          | Object creation    |
| (iv) petrolPrice++;                    | Increment          |

(c)  
| switch Statement                         | if-else Statement                      |
|------------------------------------------|----------------------------------------|
| Works only with specific values          | Works with both conditions and ranges  |
| Cannot evaluate relational expressions   | Can evaluate relational expressions    |

(d)  
An **infinite loop** is a loop that never ends because the condition always remains true.

Example:
```java
while(true) { }
```

## Q3

(c)  
| Variable | Value              |
|----------|--------------------|
| x        | 7.0  (`Math.ceil(6.35) = 7`, `Math.abs(7) = 7`)   |
| y        | 15.0 (`Math.max(6.35,14.74) = 14.74`, `Math.rint(14.74) = 15`) |

(α)  
```java
String grade;
if (mark >= 90) {
    grade = "A";
} else if (mark >= 80) {
    grade = "B";
} else {
    grade = "C";
}
```

(e)  
Output:
```
6
5
```
(Note: `a(a)-(--a);` is invalid syntax and will cause a compile error; assuming it was meant to be `a = a - (--a);` then the output is above.)

(h)  
(1) The inner loop runs 2 times for each of the 3 iterations of the outer loop, so total executions = 3 × 2 = 6 times.  
(2) The variable `number` stores integer values in the range 0 to 9 (inclusive).

## Q4

(i)  
```
x=1001
y=1001.0
```

(ii)  
```
The King said "Begin at the beginning!" to me.
```

## Q5

```java
import java.util.Scanner;

public class SpecialTwoDigit {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter a two-digit number: ");
        int num = sc.nextInt();

        if (num < 10 || num > 99) {
            System.out.println("Not a Special 2-digit number");
            return;
        }

        int tens = num / 10;
        int units = num % 10;
        int sum = tens + units;
        int product = tens * units;
        int total = sum + product;

        if (total == num)
            System.out.println("Special 2-digit number");
        else
            System.out.println("Not a Special 2-digit number");
    }
}
```

## Q8

```java 
import java.util.Scanner;

public class BankDepositCalculator {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int choice;

        do {
            System.out.println("\nBank Deposit Calculator Menu:");
            System.out.println("1. Term Deposit");
            System.out.println("2. Recurring Deposit");
            System.out.println("3. Exit");
            System.out.print("Enter your choice: ");
            choice = scanner.nextInt();

            switch (choice) {
                case 1:
                    calculateTermDeposit(scanner);
                    break;
                case 2:
                    calculateRecurringDeposit(scanner);
                    break;
                case 3:
                    System.out.println("Exiting the calculator. Goodbye!");
                    break;
                default:
                    System.out.println("Invalid choice. Please try again.");
            }
        } while (choice != 3);

        scanner.close();
    }

    public static void calculateTermDeposit(Scanner scanner) {
        System.out.println("\nCalculating Term Deposit Maturity Amount:");
        System.out.print("Enter Principal (P): ");
        double principal = scanner.nextDouble();
        System.out.print("Enter Rate of Interest (r) in %: ");
        double rate = scanner.nextDouble();
        System.out.print("Enter Time Period (n) in years: ");
        int time = scanner.nextInt();

        double maturityAmount = principal * Math.pow(1 + (rate / 100), time);
        System.out.println("Maturity Amount (A) = " + String.format("%.2f", maturityAmount));
    }

    public static void calculateRecurringDeposit(Scanner scanner) {
        System.out.println("\nCalculating Recurring Deposit Maturity Amount:");
        System.out.print("Enter Monthly Installment (P): ");
        double monthlyInstallment = scanner.nextDouble();
        System.out.print("Enter Rate of Interest (r) in % per annum: ");
        double annualRate = scanner.nextDouble();
        System.out.print("Enter Time Period (n) in months: ");
        int months = scanner.nextInt();

        double monthlyRate = annualRate / (100 * 12);
        double maturityAmount = monthlyInstallment * months + monthlyInstallment * (months * (months + 1) / 2.0) * monthlyRate;
        System.out.println("Maturity Amount (A) = " + String.format("%.2f", maturityAmount));
    }
}
```