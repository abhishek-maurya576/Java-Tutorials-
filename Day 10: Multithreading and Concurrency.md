### Day 10: Multithreading and Concurrency

#### Topics

1. **Introduction to Multithreading**
   - **Definition:**
     Multithreading in Java is a process of executing multiple threads simultaneously to maximize the utilization of CPU.
   - **Thread Class and Runnable Interface:**
     - **Thread Class:** Provides constructors and methods for creating and operating on threads.
     - **Runnable Interface:** Should be implemented by any class whose instances are intended to be executed by a thread.

2. **Creating Threads**
   - **Extending Thread Class:**
     ```java
     class MyThread extends Thread {
         public void run() {
             System.out.println("Thread is running.");
         }
     }

     public class Main {
         public static void main(String[] args) {
             MyThread t1 = new MyThread();
             t1.start();
         }
     }
     ```
   - **Implementing Runnable Interface:**
     ```java
     class MyRunnable implements Runnable {
         public void run() {
             System.out.println("Thread is running.");
         }
     }

     public class Main {
         public static void main(String[] args) {
             Thread t1 = new Thread(new MyRunnable());
             t1.start();
         }
     }
     ```

3. **Thread Lifecycle**
   - **New, Runnable, Blocked, Waiting, Timed Waiting, Terminated:**
     - **New:** A thread that is created but not started.
     - **Runnable:** A thread that is ready to run but waiting for CPU time.
     - **Blocked:** A thread that is blocked waiting for a monitor lock.
     - **Waiting:** A thread that is waiting indefinitely for another thread to perform a particular action.
     - **Timed Waiting:** A thread that is waiting for another thread to perform a particular action within a stipulated amount of time.
     - **Terminated:** A thread that has exited.

4. **Thread Methods**
   - **Common Methods:**
     - `start()`: Starts the execution of the thread.
     - `run()`: Entry point for the thread.
     - `sleep(long millis)`: Causes the currently executing thread to sleep for the specified number of milliseconds.
     - `join()`: Waits for a thread to die.
     - `yield()`: Causes the currently executing thread object to temporarily pause and allow other threads to execute.
     - `setPriority(int newPriority)`: Changes the priority of the thread.
     - `getName()`: Returns the name of the thread.
     - `setName(String name)`: Changes the name of the thread.
     - `isAlive()`: Tests if the thread is alive.

5. **Synchronization**
   - **Definition:**
     Synchronization in Java is the capability to control the access of multiple threads to shared resources.
   - **Synchronized Methods and Blocks:**
     - **Synchronized Method:**
       ```java
       synchronized void printTable(int n) {
           for (int i = 1; i <= 5; i++) {
               System.out.println(n * i);
           }
       }
       ```
     - **Synchronized Block:**
       ```java
       void printTable(int n) {
           synchronized(this) {
               for (int i = 1; i <= 5; i++) {
                   System.out.println(n * i);
               }
           }
       }
       ```

6. **Inter-thread Communication**
   - **wait(), notify(), and notifyAll():**
     - `wait()`: Causes the current thread to wait until another thread invokes `notify()`.
     - `notify()`: Wakes up a single thread that is waiting on this object's monitor.
     - `notifyAll()`: Wakes up all threads that are waiting on this object's monitor.

7. **Deadlock**
   - **Definition:**
     Deadlock is a condition where two or more threads are blocked forever, waiting for each other.
   - **Example:**
     ```java
     class A {
         synchronized void methodA(B b) {
             b.last();
         }

         synchronized void last() {}
     }

     class B {
         synchronized void methodB(A a) {
             a.last();
         }

         synchronized void last() {}
     }

     public class Deadlock {
         public static void main(String[] args) {
             final A a = new A();
             final B b = new B();

             Thread t1 = new Thread(() -> a.methodA(b));
             Thread t2 = new Thread(() -> b.methodB(a));

             t1.start();
             t2.start();
         }
     }
     ```

8. **Concurrency Utilities (java.util.concurrent)**
   - **Executor Framework:**
     - **Example:**
       ```java
       import java.util.concurrent.ExecutorService;
       import java.util.concurrent.Executors;

       public class Main {
           public static void main(String[] args) {
               ExecutorService executor = Executors.newFixedThreadPool(2);
               executor.submit(() -> System.out.println("Task 1"));
               executor.submit(() -> System.out.println("Task 2"));
               executor.shutdown();
           }
       }
       ```
   - **Callable and Future:**
     - **Example:**
       ```java
       import java.util.concurrent.Callable;
       import java.util.concurrent.ExecutionException;
       import java.util.concurrent.ExecutorService;
       import java.util.concurrent.Executors;
       import java.util.concurrent.Future;

       public class Main {
           public static void main(String[] args) {
               ExecutorService executor = Executors.newFixedThreadPool(1);
               Callable<String> callable = () -> "Hello, World!";
               Future<String> future = executor.submit(callable);

               try {
                   System.out.println(future.get());
               } catch (InterruptedException | ExecutionException e) {
                   e.printStackTrace();
               }

               executor.shutdown();
           }
       }
       ```
   - **Locks, Conditions, and Semaphores:**
     - **Example:**
       ```java
       import java.util.concurrent.locks.Lock;
       import java.util.concurrent.locks.ReentrantLock;

       public class Main {
           public static void main(String[] args) {
               Lock lock = new ReentrantLock();

               new Thread(() -> {
                   lock.lock();
                   try {
                       System.out.println("Thread 1");
                   } finally {
                       lock.unlock();
                   }
               }).start();

               new Thread(() -> {
                   lock.lock();
                   try {
                       System.out.println("Thread 2");
                   } finally {
                       lock.unlock();
                   }
               }).start();
           }
       }
       ```

#### Tasks

1. **Create a Thread:**
   - Implement a thread by extending the `Thread` class and implementing the `Runnable` interface.
   
2. **Thread Lifecycle:**
   - Write a program that demonstrates the lifecycle of a thread.
   
3. **Synchronization:**
   - Create a program that shows the use of synchronized methods and blocks.
   
4. **Inter-thread Communication:**
   - Write a program that demonstrates the use of `wait()`, `notify()`, and `notifyAll()` methods.

5. **Deadlock:**
   - Create a scenario that leads to a deadlock and then resolve it.

6. **Concurrency Utilities:**
   - Use the Executor framework to execute multiple threads.
   - Implement a task using `Callable` and retrieve the result using `Future`.

#### Resources

- [Java Multithreading](https://docs.oracle.com/javase/tutorial/essential/concurrency/)
- [Java Concurrency Utilities](https://docs.oracle.com/javase/8/docs/technotes/guides/concurrency/)

#### Example Code

**Thread Example:**
```java
class MyThread extends Thread {
    public void run() {
        System.out.println("Thread is running.");
    }
}

public class Main {
    public static void main(String[] args) {
        MyThread t1 = new MyThread();
        t1.start();
    }
}
```

**Runnable Example:**
```java
class MyRunnable implements Runnable {
    public void run() {
        System.out.println("Thread is running.");
    }
}

public class Main {
    public static void main(String[] args) {
        Thread t1 = new Thread(new MyRunnable());
        t1.start();
    }
}
```

**Synchronization Example:**
```java
class Table {
    synchronized void printTable(int n) {
        for (int i = 1; i <= 5; i++) {
            System.out.println(n * i);
            try {
                Thread.sleep(400);
            } catch (Exception e) {
                System.out.println(e);
            }
        }
    }
}

public class Main {
    public static void main(String[] args) {
        final Table obj = new Table();

        Thread t1 = new Thread(() -> obj.printTable(5));
        Thread t2 = new Thread(() -> obj.printTable(100));

        t1.start();
        t2.start();
    }
}
```

**Inter-thread Communication Example:**
```java
class SharedResource {
    synchronized void waitMethod() {
        try {
            wait();
            System.out.println("After wait");
        } catch (InterruptedException e) {
            System.out.println(e);
        }
    }

    synchronized void notifyMethod() {
        notify();
        System.out.println("After notify");
    }
}

public class Main {
    public static void main(String[] args) {
        final SharedResource resource = new SharedResource();

        Thread t1 = new Thread(resource::waitMethod);
        Thread t2 = new Thread(resource::notifyMethod);

        t1.start();
        t2.start();
    }
}
```

**Executor Framework Example:**
```java
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;

public class Main {
    public static void main(String[] args) {
        ExecutorService executor = Executors.newFixedThreadPool(2);
        executor.submit(() -> System.out.println("Task 

1"));
        executor.submit(() -> System.out.println("Task 2"));
        executor.shutdown();
    }
}
```
