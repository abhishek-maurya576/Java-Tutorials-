### Day 6: Advanced Object-Oriented Programming (OOP) Concepts

#### Topics

1. **Polymorphism**
   - **Method Overriding**
     - **Definition:**
       Overriding occurs when a subclass provides a specific implementation of a method that is already defined in its superclass.
     - **Example:**
       ```java
       class Animal {
           void makeSound() {
               System.out.println("Animal makes a sound");
           }
       }

       class Dog extends Animal {
           @Override
           void makeSound() {
               System.out.println("Dog barks");
           }
       }

       public class Main {
           public static void main(String[] args) {
               Animal myDog = new Dog();
               myDog.makeSound(); // Dog barks
           }
       }
       ```

   - **Dynamic Method Dispatch**
     - **Definition:**
       Dynamic method dispatch is the mechanism by which a call to an overridden method is resolved at runtime rather than compile-time.
     - **Example:**
       ```java
       class Animal {
           void makeSound() {
               System.out.println("Animal makes a sound");
           }
       }

       class Dog extends Animal {
           @Override
           void makeSound() {
               System.out.println("Dog barks");
           }
       }

       class Cat extends Animal {
           @Override
           void makeSound() {
               System.out.println("Cat meows");
           }
       }

       public class Main {
           public static void main(String[] args) {
               Animal myAnimal;

               myAnimal = new Dog();
               myAnimal.makeSound(); // Dog barks

               myAnimal = new Cat();
               myAnimal.makeSound(); // Cat meows
           }
       }
       ```

2. **Abstract Classes and Methods**
   - **Definition:**
     An abstract class is a class that cannot be instantiated and may contain abstract methods that must be implemented by subclasses.
   - **Syntax:**
     ```java
     abstract class Animal {
         abstract void makeSound();
     }

     class Dog extends Animal {
         @Override
         void makeSound() {
             System.out.println("Dog barks");
         }
     }

     public class Main {
         public static void main(String[] args) {
             Animal myDog = new Dog();
             myDog.makeSound(); // Dog barks
         }
     }
     ```

3. **Interfaces**
   - **Definition:**
     An interface in Java is a reference type, similar to a class, that can contain only constants, method signatures, default methods, static methods, and nested types. Interfaces cannot contain instance fields or constructors.
   - **Syntax:**
     ```java
     interface Animal {
         void makeSound();
     }

     class Dog implements Animal {
         @Override
         public void makeSound() {
             System.out.println("Dog barks");
         }
     }

     public class Main {
         public static void main(String[] args) {
             Animal myDog = new Dog();
             myDog.makeSound(); // Dog barks
         }
     }
     ```

4. **Packages and Access Modifiers**
   - **Packages:**
     - **Definition:**
       A package in Java is used to group related classes. Packages provide access protection and namespace management.
     - **Syntax:**
       ```java
       package mypackage;

       public class MyClass {
           // class body
       }
       ```

   - **Access Modifiers:**
     - **Public:** The class, method, or field is accessible from any other class.
     - **Private:** The method or field is accessible only within its own class.
     - **Protected:** The method or field is accessible within its own package and by subclasses.
     - **Default (no modifier):** The method or field is accessible only within its own package.

#### Tasks

1. **Method Overriding:**
   - Create a base class `Vehicle` with a method `move()`.
   - Create a subclass `Car` that overrides the `move()` method.
   - Demonstrate method overriding by creating objects of `Vehicle` and `Car`.

2. **Abstract Classes and Methods:**
   - Create an abstract class `Shape` with an abstract method `draw()`.
   - Create subclasses `Circle` and `Rectangle` that implement the `draw()` method.
   - Demonstrate abstract classes by creating objects of `Circle` and `Rectangle`.

3. **Interfaces:**
   - Create an interface `Animal` with a method `makeSound()`.
   - Create classes `Dog` and `Cat` that implement the `Animal` interface.
   - Demonstrate interfaces by creating objects of `Dog` and `Cat`.

4. **Packages:**
   - Create a package `mypackage`.
   - Create a class `MyClass` in the `mypackage` package with a public method `display()`.
   - Create another class in a different package that uses the `MyClass` from `mypackage`.

#### Resources

- [Java Polymorphism](https://docs.oracle.com/javase/tutorial/java/IandI/polymorphism.html)
- [Java Abstract Classes](https://docs.oracle.com/javase/tutorial/java/IandI/abstract.html)
- [Java Interfaces](https://docs.oracle.com/javase/tutorial/java/IandI/createinterface.html)
- [Java Packages](https://docs.oracle.com/javase/tutorial/java/package/packages.html)
- [Java Access Modifiers](https://docs.oracle.com/javase/tutorial/java/javaOO/accesscontrol.html)

#### Example Code

**Method Overriding Example:**
```java
class Vehicle {
    void move() {
        System.out.println("Vehicle is moving");
    }
}

class Car extends Vehicle {
    @Override
    void move() {
        System.out.println("Car is moving");
    }
}

public class Main {
    public static void main(String[] args) {
        Vehicle myCar = new Car();
        myCar.move(); // Car is moving
    }
}
```

**Abstract Class Example:**
```java
abstract class Shape {
    abstract void draw();
}

class Circle extends Shape {
    @Override
    void draw() {
        System.out.println("Drawing a Circle");
    }
}

class Rectangle extends Shape {
    @Override
    void draw() {
        System.out.println("Drawing a Rectangle");
    }
}

public class Main {
    public static void main(String[] args) {
        Shape myCircle = new Circle();
        Shape myRectangle = new Rectangle();

        myCircle.draw(); // Drawing a Circle
        myRectangle.draw(); // Drawing a Rectangle
    }
}
```

**Interface Example:**
```java
interface Animal {
    void makeSound();
}

class Dog implements Animal {
    @Override
    public void makeSound() {
        System.out.println("Dog barks");
    }
}

class Cat implements Animal {
    @Override
    public void makeSound() {
        System.out.println("Cat meows");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal myDog = new Dog();
        Animal myCat = new Cat();

        myDog.makeSound(); // Dog barks
        myCat.makeSound(); // Cat meows
    }
}
```

**Package Example:**
```java
// File: mypackage/MyClass.java
package mypackage;

public class MyClass {
    public void display() {
        System.out.println("Hello from MyClass in mypackage");
    }
}

// File: Main.java
import mypackage.MyClass;

public class Main {
    public static void main(String[] args) {
        MyClass obj = new MyClass();
        obj.display(); // Hello from MyClass in mypackage
    }
}
```

