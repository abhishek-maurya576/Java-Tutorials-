### Day 3: Control Flow Statements

#### Topics

1. **If-Else Statements**
   - **Syntax:**
     ```java
     if (condition) {
         // code to be executed if condition is true
     } else {
         // code to be executed if condition is false
     }
     ```
   - **Example:**
     ```java
     int number = 10;
     if (number > 0) {
         System.out.println("The number is positive.");
     } else {
         System.out.println("The number is not positive.");
     }
     ```

2. **Switch Statements**
   - **Syntax:**
     ```java
     switch (variable) {
         case value1:
             // code to be executed if variable == value1
             break;
         case value2:
             // code to be executed if variable == value2
             break;
         // more cases
         default:
             // code to be executed if variable doesn't match any case
     }
     ```
   - **Example:**
     ```java
     int day = 3;
     switch (day) {
         case 1:
             System.out.println("Monday");
             break;
         case 2:
             System.out.println("Tuesday");
             break;
         case 3:
             System.out.println("Wednesday");
             break;
         // more cases
         default:
             System.out.println("Invalid day");
     }
     ```

3. **Loops**
   - **For Loop:**
     - **Syntax:**
       ```java
       for (initialization; condition; increment/decrement) {
           // code to be executed
       }
       ```
     - **Example:**
       ```java
       for (int i = 0; i < 5; i++) {
           System.out.println("i: " + i);
       }
       ```

   - **While Loop:**
     - **Syntax:**
       ```java
       while (condition) {
           // code to be executed
       }
       ```
     - **Example:**
       ```java
       int i = 0;
       while (i < 5) {
           System.out.println("i: " + i);
           i++;
       }
       ```

   - **Do-While Loop:**
     - **Syntax:**
       ```java
       do {
           // code to be executed
       } while (condition);
       ```
     - **Example:**
       ```java
       int i = 0;
       do {
           System.out.println("i: " + i);
           i++;
       } while (i < 5);
       ```

#### Tasks

1. **Write a Program Using If-Else:**
   - Write a program that checks if a number is positive, negative, or zero.

2. **Write a Program Using Switch:**
   - Write a program that prints the name of the day based on the day number (1-7).

3. **Write Programs Using Loops:**
   - Write a program that prints numbers from 1 to 10 using a for loop.
   - Write a program that prints even numbers from 1 to 20 using a while loop.
   - Write a program that prints numbers from 10 to 1 using a do-while loop.

#### Resources

- [Java If-Else](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/if.html)
- [Java Switch](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/switch.html)
- [Java For Loop](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/for.html)
- [Java While Loop](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/while.html)

#### Example Code

**If-Else Statement:**
```java
public class IfElseExample {
    public static void main(String[] args) {
        int number = 10;
        if (number > 0) {
            System.out.println("The number is positive.");
        } else if (number < 0) {
            System.out.println("The number is negative.");
        } else {
            System.out.println("The number is zero.");
        }
    }
}
```

**Switch Statement:**
```java
public class SwitchExample {
    public static void main(String[] args) {
        int day = 3;
        switch (day) {
            case 1:
                System.out.println("Monday");
                break;
            case 2:
                System.out.println("Tuesday");
                break;
            case 3:
                System.out.println("Wednesday");
                break;
            case 4:
                System.out.println("Thursday");
                break;
            case 5:
                System.out.println("Friday");
                break;
            case 6:
                System.out.println("Saturday");
                break;
            case 7:
                System.out.println("Sunday");
                break;
            default:
                System.out.println("Invalid day");
        }
    }
}
```

**For Loop:**
```java
public class ForLoopExample {
    public static void main(String[] args) {
        for (int i = 1; i <= 10; i++) {
            System.out.println(i);
        }
    }
}
```

**While Loop:**
```java
public class WhileLoopExample {
    public static void main(String[] args) {
        int i = 1;
        while (i <= 20) {
            if (i % 2 == 0) {
                System.out.println(i);
            }
            i++;
        }
    }
}
```

**Do-While Loop:**
```java
public class DoWhileLoopExample {
    public static void main(String[] args) {
        int i = 10;
        do {
            System.out.println(i);
            i--;
        } while (i > 0);
    }
}
```
