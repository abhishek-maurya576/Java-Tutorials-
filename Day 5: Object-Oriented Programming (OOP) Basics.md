### Day 5: Object-Oriented Programming (OOP) Basics

#### Topics

1. **Introduction to Object-Oriented Programming (OOP)**
   - **Concepts:**
     - **Class:** A blueprint for creating objects (a particular data structure).
     - **Object:** An instance of a class.
     - **Encapsulation:** Wrapping data (variables) and code (methods) together as a single unit.
     - **Inheritance:** Mechanism where one class acquires the properties and behaviors of a parent class.
     - **Polymorphism:** Ability to process objects differently based on their data type or class.
     - **Abstraction:** Hiding the complex implementation details and showing only the essential features.

2. **Creating Classes and Objects**
   - **Defining a Class:**
     ```java
     public class Person {
         String name;
         int age;

         void speak() {
             System.out.println("Hello, my name is " + name);
         }
     }
     ```
   - **Creating an Object:**
     ```java
     public class Main {
         public static void main(String[] args) {
             Person person1 = new Person();
             person1.name = "John";
             person1.age = 30;
             person1.speak();
         }
     }
     ```

3. **Constructors**
   - **Default Constructor:**
     ```java
     public class Person {
         String name;
         int age;

         // Default constructor
         public Person() {
             this.name = "Unknown";
             this.age = 0;
         }

         void speak() {
             System.out.println("Hello, my name is " + name);
         }
     }
     ```
   - **Parameterized Constructor:**
     ```java
     public class Person {
         String name;
         int age;

         // Parameterized constructor
         public Person(String name, int age) {
             this.name = name;
             this.age = age;
         }

         void speak() {
             System.out.println("Hello, my name is " + name);
         }
     }
     ```

4. **Encapsulation**
   - **Private Variables and Public Methods:**
     ```java
     public class Person {
         private String name;
         private int age;

         public String getName() {
             return name;
         }

         public void setName(String name) {
             this.name = name;
         }

         public int getAge() {
             return age;
         }

         public void setAge(int age) {
             this.age = age;
         }
     }
     ```

5. **Inheritance**
   - **Base and Derived Classes:**
     ```java
     // Base class
     public class Animal {
         void eat() {
             System.out.println("This animal eats food.");
         }
     }

     // Derived class
     public class Dog extends Animal {
         void bark() {
             System.out.println("The dog barks.");
         }
     }

     public class Main {
         public static void main(String[] args) {
             Dog dog = new Dog();
             dog.eat();
             dog.bark();
         }
     }
     ```

#### Tasks

1. **Create a Class and an Object:**
   - Define a class `Car` with attributes `make`, `model`, and `year`.
   - Create an object of the `Car` class, set its attributes, and print them.

2. **Use Constructors:**
   - Add a parameterized constructor to the `Car` class.
   - Create an object using the parameterized constructor and print its attributes.

3. **Encapsulation:**
   - Modify the `Car` class to use private variables.
   - Add getter and setter methods for each variable.
   - Create an object, set its attributes using setter methods, and print them using getter methods.

4. **Inheritance:**
   - Create a base class `Vehicle` with a method `move()`.
   - Create a derived class `Bicycle` that extends `Vehicle` and adds a method `ringBell()`.
   - Create an object of the `Bicycle` class and call both methods.

#### Resources

- [Java Classes and Objects](https://docs.oracle.com/javase/tutorial/java/javaOO/classes.html)
- [Java Constructors](https://docs.oracle.com/javase/tutorial/java/javaOO/constructors.html)
- [Java Encapsulation](https://docs.oracle.com/javase/tutorial/java/javaOO/accesscontrol.html)
- [Java Inheritance](https://docs.oracle.com/javase/tutorial/java/IandI/subclasses.html)

#### Example Code

**Class and Object Example:**
```java
public class Car {
    String make;
    String model;
    int year;

    void displayInfo() {
        System.out.println("Make: " + make);
        System.out.println("Model: " + model);
        System.out.println("Year: " + year);
    }

    public static void main(String[] args) {
        Car car = new Car();
        car.make = "Toyota";
        car.model = "Corolla";
        car.year = 2020;
        car.displayInfo();
    }
}
```

**Constructor Example:**
```java
public class Car {
    String make;
    String model;
    int year;

    // Parameterized constructor
    public Car(String make, String model, int year) {
        this.make = make;
        this.model = model;
        this.year = year;
    }

    void displayInfo() {
        System.out.println("Make: " + make);
        System.out.println("Model: " + model);
        System.out.println("Year: " + year);
    }

    public static void main(String[] args) {
        Car car = new Car("Toyota", "Corolla", 2020);
        car.displayInfo();
    }
}
```

**Encapsulation Example:**
```java
public class Car {
    private String make;
    private String model;
    private int year;

    public String getMake() {
        return make;
    }

    public void setMake(String make) {
        this.make = make;
    }

    public String getModel() {
        return model;
    }

    public void setModel(String model) {
        this.model = model;
    }

    public int getYear() {
        return year;
    }

    public void setYear(int year) {
        this.year = year;
    }

    void displayInfo() {
        System.out.println("Make: " + getMake());
        System.out.println("Model: " + getModel());
        System.out.println("Year: " + getYear());
    }

    public static void main(String[] args) {
        Car car = new Car();
        car.setMake("Toyota");
        car.setModel("Corolla");
        car.setYear(2020);
        car.displayInfo();
    }
}
```

**Inheritance Example:**
```java
// Base class
public class Vehicle {
    void move() {
        System.out.println("This vehicle is moving.");
    }
}

// Derived class
public class Bicycle extends Vehicle {
    void ringBell() {
        System.out.println("The bicycle bell rings.");
    }

    public static void main(String[] args) {
        Bicycle bicycle = new Bicycle();
        bicycle.move();
        bicycle.ringBell();
    }
}
```
