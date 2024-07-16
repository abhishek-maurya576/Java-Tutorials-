### Day 8: Collections Framework and Generics

#### Topics

1. **Introduction to the Collections Framework**
   - **Definition:**
     The Collections Framework is a unified architecture for representing and manipulating collections, enabling collections to be manipulated independently of implementation details.
   - **Core Interfaces:**
     - **Collection:** The root interface in the collections hierarchy.
     - **List:** An ordered collection (also known as a sequence).
     - **Set:** A collection that does not allow duplicate elements.
     - **Queue:** A collection used to hold multiple elements prior to processing.
     - **Map:** An object that maps keys to values, with no duplicate keys allowed.

2. **List Interface and ArrayList Class**
   - **List Interface:**
     - **Example:**
       ```java
       import java.util.List;
       import java.util.ArrayList;

       public class Main {
           public static void main(String[] args) {
               List<String> list = new ArrayList<>();
               list.add("Apple");
               list.add("Banana");
               list.add("Cherry");

               for (String fruit : list) {
                   System.out.println(fruit);
               }
           }
       }
       ```

   - **ArrayList Class:**
     - **Example:**
       ```java
       import java.util.ArrayList;

       public class Main {
           public static void main(String[] args) {
               ArrayList<Integer> numbers = new ArrayList<>();
               numbers.add(1);
               numbers.add(2);
               numbers.add(3);

               for (int number : numbers) {
                   System.out.println(number);
               }
           }
       }
       ```

3. **Set Interface and HashSet Class**
   - **Set Interface:**
     - **Example:**
       ```java
       import java.util.Set;
       import java.util.HashSet;

       public class Main {
           public static void main(String[] args) {
               Set<String> set = new HashSet<>();
               set.add("Apple");
               set.add("Banana");
               set.add("Cherry");
               set.add("Apple"); // Duplicate element, will not be added

               for (String fruit : set) {
                   System.out.println(fruit);
               }
           }
       }
       ```

   - **HashSet Class:**
     - **Example:**
       ```java
       import java.util.HashSet;

       public class Main {
           public static void main(String[] args) {
               HashSet<String> set = new HashSet<>();
               set.add("Apple");
               set.add("Banana");
               set.add("Cherry");

               for (String fruit : set) {
                   System.out.println(fruit);
               }
           }
       }
       ```

4. **Map Interface and HashMap Class**
   - **Map Interface:**
     - **Example:**
       ```java
       import java.util.Map;
       import java.util.HashMap;

       public class Main {
           public static void main(String[] args) {
               Map<String, Integer> map = new HashMap<>();
               map.put("Apple", 1);
               map.put("Banana", 2);
               map.put("Cherry", 3);

               for (Map.Entry<String, Integer> entry : map.entrySet()) {
                   System.out.println(entry.getKey() + ": " + entry.getValue());
               }
           }
       }
       ```

   - **HashMap Class:**
     - **Example:**
       ```java
       import java.util.HashMap;

       public class Main {
           public static void main(String[] args) {
               HashMap<String, Integer> map = new HashMap<>();
               map.put("Apple", 1);
               map.put("Banana", 2);
               map.put("Cherry", 3);

               for (String key : map.keySet()) {
                   System.out.println(key + ": " + map.get(key));
               }
           }
       }
       ```

5. **Generics**
   - **Definition:**
     Generics enable types (classes and interfaces) to be parameters when defining classes, interfaces, and methods.
   - **Generic Class:**
     - **Example:**
       ```java
       public class Box<T> {
           private T t;

           public void set(T t) {
               this.t = t;
           }

           public T get() {
               return t;
           }

           public static void main(String[] args) {
               Box<Integer> integerBox = new Box<>();
               integerBox.set(10);
               System.out.println(integerBox.get());

               Box<String> stringBox = new Box<>();
               stringBox.set("Hello");
               System.out.println(stringBox.get());
           }
       }
       ```

   - **Generic Method:**
     - **Example:**
       ```java
       public class Main {
           public static <T> void printArray(T[] array) {
               for (T element : array) {
                   System.out.println(element);
               }
           }

           public static void main(String[] args) {
               Integer[] intArray = {1, 2, 3};
               String[] stringArray = {"Hello", "World"};

               printArray(intArray);
               printArray(stringArray);
           }
       }
       ```

#### Tasks

1. **Using ArrayList:**
   - Create an `ArrayList` of strings.
   - Add elements to the list and print them.

2. **Using HashSet:**
   - Create a `HashSet` of integers.
   - Add elements to the set and print them.

3. **Using HashMap:**
   - Create a `HashMap` with string keys and integer values.
   - Add key-value pairs to the map and print them.

4. **Using Generics:**
   - Create a generic class that can hold any type of data.
   - Create a generic method that prints an array of any type.

#### Resources

- [Java Collections Framework](https://docs.oracle.com/javase/tutorial/collections/)
- [Java Generics](https://docs.oracle.com/javase/tutorial/java/generics/)

#### Example Code

**ArrayList Example:**
```java
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();
        list.add("Apple");
        list.add("Banana");
        list.add("Cherry");

        for (String fruit : list) {
            System.out.println(fruit);
        }
    }
}
```

**HashSet Example:**
```java
import java.util.HashSet;

public class Main {
    public static void main(String[] args) {
        HashSet<Integer> set = new HashSet<>();
        set.add(1);
        set.add(2);
        set.add(3);
        set.add(1); // Duplicate element, will not be added

        for (int number : set) {
            System.out.println(number);
        }
    }
}
```

**HashMap Example:**
```java
import java.util.HashMap;

public class Main {
    public static void main(String[] args) {
        HashMap<String, Integer> map = new HashMap<>();
        map.put("Apple", 1);
        map.put("Banana", 2);
        map.put("Cherry", 3);

        for (String key : map.keySet()) {
            System.out.println(key + ": " + map.get(key));
        }
    }
}
```

**Generic Class Example:**
```java
public class Box<T> {
    private T t;

    public void set(T t) {
        this.t = t;
    }

    public T get() {
        return t;
    }

    public static void main(String[] args) {
        Box<Integer> integerBox = new Box<>();
        integerBox.set(10);
        System.out.println(integerBox.get());

        Box<String> stringBox = new Box<>();
        stringBox.set("Hello");
        System.out.println(stringBox.get());
    }
}
```

**Generic Method Example:**
```java
public class Main {
    public static <T> void printArray(T[] array) {
        for (T element : array) {
            System.out.println(element);
        }
    }

    public static void main(String[] args) {
        Integer[] intArray = {1, 2, 3};
        String[] stringArray = {"Hello", "World"};

        printArray(intArray);
        printArray(stringArray);
    }
}
```
