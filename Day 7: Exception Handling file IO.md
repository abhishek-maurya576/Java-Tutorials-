### Day 7: Exception Handling and File I/O

#### Topics

1. **Exception Handling**
   - **Definition:**
     Exception handling in Java provides a way to handle runtime errors, allowing the normal flow of the application to be maintained.
   - **Types of Exceptions:**
     - **Checked Exceptions:** These are checked at compile-time.
     - **Unchecked Exceptions:** These are checked at runtime (also known as runtime exceptions).
     - **Errors:** These are serious problems that a reasonable application should not try to catch.
   - **Try-Catch Block:**
     ```java
     try {
         // code that may throw an exception
     } catch (ExceptionType e) {
         // code to handle the exception
     }
     ```
   - **Multiple Catch Blocks:**
     ```java
     try {
         // code that may throw multiple exceptions
     } catch (ExceptionType1 e1) {
         // code to handle ExceptionType1
     } catch (ExceptionType2 e2) {
         // code to handle ExceptionType2
     }
     ```
   - **Finally Block:**
     ```java
     try {
         // code that may throw an exception
     } catch (ExceptionType e) {
         // code to handle the exception
     } finally {
         // code that will always execute
     }
     ```
   - **Throw and Throws:**
     ```java
     void method() throws ExceptionType {
         // code that may throw an exception
         throw new ExceptionType("Exception message");
     }
     ```

2. **Commonly Used Exception Classes**
   - **ArithmeticException**
   - **NullPointerException**
   - **ArrayIndexOutOfBoundsException**
   - **FileNotFoundException**
   - **IOException**

3. **Creating Custom Exceptions**
   - **Definition:**
     You can create your own exceptions in Java by extending the `Exception` class.
   - **Example:**
     ```java
     class CustomException extends Exception {
         public CustomException(String message) {
             super(message);
         }
     }

     public class Main {
         public static void main(String[] args) {
             try {
                 throw new CustomException("This is a custom exception");
             } catch (CustomException e) {
                 System.out.println(e.getMessage());
             }
         }
     }
     ```

4. **File I/O (Input/Output)**
   - **File Class:**
     ```java
     import java.io.File;

     public class Main {
         public static void main(String[] args) {
             File file = new File("filename.txt");
             if (file.exists()) {
                 System.out.println("File exists");
             } else {
                 System.out.println("File does not exist");
             }
         }
     }
     ```
   - **Reading from a File:**
     ```java
     import java.io.File;
     import java.io.FileNotFoundException;
     import java.util.Scanner;

     public class Main {
         public static void main(String[] args) {
             try {
                 File file = new File("filename.txt");
                 Scanner reader = new Scanner(file);
                 while (reader.hasNextLine()) {
                     String data = reader.nextLine();
                     System.out.println(data);
                 }
                 reader.close();
             } catch (FileNotFoundException e) {
                 System.out.println("An error occurred.");
                 e.printStackTrace();
             }
         }
     }
     ```
   - **Writing to a File:**
     ```java
     import java.io.FileWriter;
     import java.io.IOException;

     public class Main {
         public static void main(String[] args) {
             try {
                 FileWriter writer = new FileWriter("filename.txt");
                 writer.write("Hello, world!");
                 writer.close();
                 System.out.println("Successfully wrote to the file.");
             } catch (IOException e) {
                 System.out.println("An error occurred.");
                 e.printStackTrace();
             }
         }
     }
     ```

#### Tasks

1. **Exception Handling:**
   - Write a program that demonstrates the use of try-catch-finally blocks.
   - Handle multiple types of exceptions in a single try block.
   - Create and throw a custom exception.

2. **File I/O:**
   - Write a program that creates a file and writes some text to it.
   - Write a program that reads data from an existing file and prints it to the console.

#### Resources

- [Java Exception Handling](https://docs.oracle.com/javase/tutorial/essential/exceptions/)
- [Java Custom Exceptions](https://docs.oracle.com/javase/tutorial/essential/exceptions/creating.html)
- [Java File I/O](https://docs.oracle.com/javase/tutorial/essential/io/)

#### Example Code

**Exception Handling Example:**
```java
public class ExceptionHandlingExample {
    public static void main(String[] args) {
        try {
            int result = 10 / 0;
        } catch (ArithmeticException e) {
            System.out.println("ArithmeticException: " + e.getMessage());
        } finally {
            System.out.println("This is the finally block.");
        }
    }
}
```

**Custom Exception Example:**
```java
class CustomException extends Exception {
    public CustomException(String message) {
        super(message);
    }
}

public class Main {
    public static void main(String[] args) {
        try {
            throw new CustomException("This is a custom exception");
        } catch (CustomException e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**File Writing Example:**
```java
import java.io.FileWriter;
import java.io.IOException;

public class FileWritingExample {
    public static void main(String[] args) {
        try {
            FileWriter writer = new FileWriter("example.txt");
            writer.write("Hello, world!");
            writer.close();
            System.out.println("Successfully wrote to the file.");
        } catch (IOException e) {
            System.out.println("An error occurred.");
            e.printStackTrace();
        }
    }
}
```

**File Reading Example:**
```java
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class FileReadingExample {
    public static void main(String[] args) {
        try {
            File file = new File("example.txt");
            Scanner reader = new Scanner(file);
            while (reader.hasNextLine()) {
                String data = reader.nextLine();
                System.out.println(data);
            }
            reader.close();
        } catch (FileNotFoundException e) {
            System.out.println("An error occurred.");
            e.printStackTrace();
        }
    }
}
```
