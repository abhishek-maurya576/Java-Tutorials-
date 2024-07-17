### Day 9: Advanced Java Concepts - Lambda Expressions and Stream API

#### Topics

1. **Lambda Expressions**
   - **Definition:**
     Lambda expressions provide a clear and concise way to represent one method interface using an expression. They enable functional programming in Java.
   - **Syntax:**
     ```java
     (parameters) -> expression
     (parameters) -> { statements; }
     ```
   - **Examples:**
     ```java
     // Without lambda expression
     Runnable r1 = new Runnable() {
         @Override
         public void run() {
             System.out.println("Hello, World!");
         }
     };

     // With lambda expression
     Runnable r2 = () -> System.out.println("Hello, World!");
     ```

2. **Functional Interfaces**
   - **Definition:**
     A functional interface is an interface with exactly one abstract method, and they can contain multiple default or static methods.
   - **Examples:**
     ```java
     @FunctionalInterface
     interface MyFunctionalInterface {
         void myMethod();
     }

     // Using lambda with functional interface
     MyFunctionalInterface func = () -> System.out.println("My Method");
     func.myMethod();
     ```
   - **Common Functional Interfaces in Java:**
     - **Predicate:** Represents a predicate (boolean-valued function) of one argument.
       ```java
       Predicate<Integer> isEven = (n) -> n % 2 == 0;
       System.out.println(isEven.test(4)); // true
       ```
     - **Consumer:** Represents an operation that accepts a single input argument and returns no result.
       ```java
       Consumer<String> print = (s) -> System.out.println(s);
       print.accept("Hello"); // Hello
       ```
     - **Function:** Represents a function that accepts one argument and produces a result.
       ```java
       Function<String, Integer> length = (s) -> s.length();
       System.out.println(length.apply("Hello")); // 5
       ```

3. **Stream API**
   - **Definition:**
     The Stream API is used for processing sequences of elements. It provides operations to filter, map, and reduce data in a declarative way.
   - **Creating Streams:**
     ```java
     List<String> list = Arrays.asList("a", "b", "c");
     Stream<String> stream = list.stream();
     Stream<String> parallelStream = list.parallelStream();
     ```
   - **Intermediate Operations:**
     - **filter:** 
       ```java
       List<String> filtered = list.stream()
                                   .filter(s -> s.startsWith("a"))
                                   .collect(Collectors.toList());
       ```
     - **map:**
       ```java
       List<Integer> lengths = list.stream()
                                   .map(String::length)
                                   .collect(Collectors.toList());
       ```
     - **sorted:**
       ```java
       List<String> sorted = list.stream()
                                 .sorted()
                                 .collect(Collectors.toList());
       ```
   - **Terminal Operations:**
     - **forEach:**
       ```java
       list.stream().forEach(System.out::println);
       ```
     - **collect:**
       ```java
       List<String> result = list.stream()
                                 .collect(Collectors.toList());
       ```
     - **reduce:**
       ```java
       Optional<String> concatenated = list.stream()
                                           .reduce((s1, s2) -> s1 + s2);
       concatenated.ifPresent(System.out::println);
       ```

4. **Practical Examples with Streams**
   - **Filter, Map, and Reduce:**
     ```java
     List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);

     // Filter out even numbers
     List<Integer> evenNumbers = numbers.stream()
                                        .filter(n -> n % 2 == 0)
                                        .collect(Collectors.toList());

     // Square each number
     List<Integer> squaredNumbers = numbers.stream()
                                           .map(n -> n * n)
                                           .collect(Collectors.toList());

     // Sum of all numbers
     int sum = numbers.stream()
                      .reduce(0, (a, b) -> a + b);
     ```

5. **Combining Functional Interfaces and Streams**
   - **Example:**
     ```java
     List<String> names = Arrays.asList("Alice", "Bob", "Charlie");

     // Filter names starting with 'A', convert to uppercase, and sort
     List<String> result = names.stream()
                                .filter(name -> name.startsWith("A"))
                                .map(String::toUpperCase)
                                .sorted()
                                .collect(Collectors.toList());

     result.forEach(System.out::println); // ALICE
     ```

#### Tasks

1. **Lambda Expressions:**
   - Write a lambda expression for a Runnable interface.
   - Use a lambda expression to implement a custom functional interface.

2. **Functional Interfaces:**
   - Use `Predicate` to filter a list of integers.
   - Use `Consumer` to print elements of a list.
   - Use `Function` to convert a list of strings to their lengths.

3. **Stream API:**
   - Create a stream from a list of integers and filter out the odd numbers.
   - Use a stream to sort a list of strings in alphabetical order.
   - Use a stream to map a list of strings to their lengths and collect the results.

4. **Practical Example:**
   - Write a program that takes a list of names, filters those starting with a particular letter, converts them to uppercase, sorts them, and prints the results.

#### Resources

- [Java Lambda Expressions](https://docs.oracle.com/javase/tutorial/java/javaOO/lambdaexpressions.html)
- [Java Functional Interfaces](https://docs.oracle.com/javase/tutorial/java/generics/functionalInterfaces.html)
- [Java Stream API](https://docs.oracle.com/javase/tutorial/collections/streams/)

#### Example Code

**Lambda Expression Example:**
```java
public class LambdaExample {
    public static void main(String[] args) {
        Runnable r = () -> System.out.println("Hello, World!");
        new Thread(r).start();
    }
}
```

**Functional Interface Example:**
```java
@FunctionalInterface
interface MyFunctionalInterface {
    void myMethod();
}

public class FunctionalInterfaceExample {
    public static void main(String[] args) {
        MyFunctionalInterface func = () -> System.out.println("My Method");
        func.myMethod();
    }
}
```

**Stream API Example:**
```java
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

public class StreamExample {
    public static void main(String[] args) {
        List<String> names = Arrays.asList("Alice", "Bob", "Charlie");

        List<String> result = names.stream()
                                   .filter(name -> name.startsWith("A"))
                                   .map(String::toUpperCase)
                                   .sorted()
                                   .collect(Collectors.toList());

        result.forEach(System.out::println); // ALICE
    }
}
```

