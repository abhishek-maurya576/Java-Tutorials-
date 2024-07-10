### Day 4: Methods and Arrays

#### Topics

1. **Methods**
   - **Defining Methods:**
     ```java
     public static returnType methodName(parameters) {
         // method body
         return value;
     }
     ```
   - **Calling Methods:**
     ```java
     methodName(arguments);
     ```
   - **Example:**
     ```java
     public class MethodsExample {
         public static void main(String[] args) {
             int result = add(5, 3);
             System.out.println("Sum: " + result);
         }

         public static int add(int a, int b) {
             return a + b;
         }
     }
     ```

2. **Method Overloading**
   - **Definition:**
     Method overloading allows a class to have more than one method with the same name, provided their parameter lists are different.
   - **Example:**
     ```java
     public class OverloadingExample {
         public static void main(String[] args) {
             System.out.println(add(5, 3)); // Calls the first add method
             System.out.println(add(5.0, 3.0)); // Calls the second add method
         }

         public static int add(int a, int b) {
             return a + b;
         }

         public static double add(double a, double b) {
             return a + b;
         }
     }
     ```

3. **Arrays**
   - **Declaring and Initializing Arrays:**
     ```java
     int[] myArray = new int[5];
     int[] myArray = {1, 2, 3, 4, 5};
     ```
   - **Accessing Array Elements:**
     ```java
     int value = myArray[0];
     ```
   - **Looping through Arrays:**
     ```java
     for (int i = 0; i < myArray.length; i++) {
         System.out.println(myArray[i]);
     }
     ```
   - **Example:**
     ```java
     public class ArraysExample {
         public static void main(String[] args) {
             int[] numbers = {1, 2, 3, 4, 5};

             for (int i = 0; i < numbers.length; i++) {
                 System.out.println("Element at index " + i + ": " + numbers[i]);
             }
         }
     }
     ```

4. **Multidimensional Arrays**
   - **Declaring and Initializing Multidimensional Arrays:**
     ```java
     int[][] matrix = {
         {1, 2, 3},
         {4, 5, 6},
         {7, 8, 9}
     };
     ```
   - **Accessing Elements in Multidimensional Arrays:**
     ```java
     int value = matrix[0][1];
     ```
   - **Example:**
     ```java
     public class MultidimensionalArraysExample {
         public static void main(String[] args) {
             int[][] matrix = {
                 {1, 2, 3},
                 {4, 5, 6},
                 {7, 8, 9}
             };

             for (int i = 0; i < matrix.length; i++) {
                 for (int j = 0; j < matrix[i].length; j++) {
                     System.out.print(matrix[i][j] + " ");
                 }
                 System.out.println();
             }
         }
     }
     ```

#### Tasks

1. **Write a Method to Find the Maximum of Two Numbers:**
   - Define a method `max(int a, int b)` that returns the maximum of two numbers.
   - Call this method from the `main` method and print the result.

2. **Overload a Method to Find the Maximum of Two Numbers:**
   - Overload the `max` method to work with `double` parameters.
   - Call both versions of the `max` method from the `main` method and print the results.

3. **Work with Arrays:**
   - Declare an array of integers with values `{1, 2, 3, 4, 5}`.
   - Write a loop to print all elements of the array.
   - Write a method `sumArray` that takes an array of integers and returns the sum of all elements.

4. **Work with Multidimensional Arrays:**
   - Declare and initialize a 3x3 matrix with values from 1 to 9.
   - Write a loop to print all elements of the matrix.

#### Resources

- [Java Methods](https://docs.oracle.com/javase/tutorial/java/javaOO/methods.html)
- [Java Arrays](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/arrays.html)
- [Java Multidimensional Arrays](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/arrays.html#multidim)

#### Example Code

**Method to Find Maximum of Two Numbers:**
```java
public class MethodsExample {
    public static void main(String[] args) {
        int maxInt = max(5, 3);
        double maxDouble = max(5.0, 3.0);

        System.out.println("Maximum of 5 and 3: " + maxInt);
        System.out.println("Maximum of 5.0 and 3.0: " + maxDouble);
    }

    public static int max(int a, int b) {
        return a > b ? a : b;
    }

    public static double max(double a, double b) {
        return a > b ? a : b;
    }
}
```

**Array Example:**
```java
public class ArraysExample {
    public static void main(String[] args) {
        int[] numbers = {1, 2, 3, 4, 5};
        for (int i = 0; i < numbers.length; i++) {
            System.out.println("Element at index " + i + ": " + numbers[i]);
        }

        int sum = sumArray(numbers);
        System.out.println("Sum of array elements: " + sum);
    }

    public static int sumArray(int[] array) {
        int sum = 0;
        for (int i = 0; i < array.length; i++) {
            sum += array[i];
        }
        return sum;
    }
}
```

**Multidimensional Array Example:**
```java
public class MultidimensionalArraysExample {
    public static void main(String[] args) {
        int[][] matrix = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };

        for (int i = 0; i < matrix.length; i++) {
            for (int j = 0; j < matrix[i].length; j++) {
                System.out.print(matrix[i][j] + " ");
            }
            System.out.println();
        }
    }
}
```

