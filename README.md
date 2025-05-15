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
java.util
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

```ComputerApplications
false
```

