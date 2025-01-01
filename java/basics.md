# Java Programming Basics

## **1. Java Program Structure**
A basic Java program has the following structure:  
```java
// Package declaration (optional)
package mypackage;

// Import statements (optional)
import java.util.Scanner;

// Class definition
public class Main {
    // Main method
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```
- **Package**: Organizes classes into namespaces (like folders).  
- **Import**: Brings additional functionality from libraries.  
- **Class**: A blueprint for objects.  
- **Main Method**: The entry point of the application.  

---

## **2. Comments in Java**
Comments are used to describe the code.  
- **Single-line comment**: `// This is a comment`  
- **Multi-line comment**:  
  ```java
  /* 
   This is a multi-line comment 
   explaining code 
   */
  ```
- **Documentation comment**:  
  ```java
  /**
   * This method prints a message.
   */
  public void printMessage() {
      System.out.println("Hello!");
  }
  ```

---

## **3. Variables and Data Types**
Variables store data. Java has **two types of data**:
1. **Primitive Data Types**
   - Example:
     ```java
     int age = 25;           // Integer
     double salary = 45000.5; // Decimal
     char grade = 'A';       // Character
     boolean isJavaFun = true; // Boolean
     ```

2. **Non-Primitive Data Types**
   - Example:
     ```java
     String name = "John";   // String
     int[] numbers = {1, 2, 3}; // Array
     ```

---

## **4. Operators**
Operators perform operations on variables and values.  
### **Arithmetic Operators**
- **Use Case**: Calculations  
  ```java
  int a = 10, b = 5;
  System.out.println(a + b); // Addition
  System.out.println(a * b); // Multiplication
  ```

### **Relational Operators**
- **Use Case**: Comparisons  
  ```java
  int x = 10, y = 20;
  System.out.println(x > y); // false
  System.out.println(x == y); // false
  ```

### **Logical Operators**
- **Use Case**: Combine conditions  
  ```java
  boolean cond1 = true, cond2 = false;
  System.out.println(cond1 && cond2); // AND: false
  System.out.println(cond1 || cond2); // OR: true
  ```

---

## **5. Control Statements**
Control the flow of execution.

### **Conditional Statements**
1. **If-else**
   - **Use Case**: Check age eligibility  
     ```java
     int age = 18;
     if (age >= 18) {
         System.out.println("You can vote.");
     } else {
         System.out.println("You cannot vote.");
     }
     ```

2. **Switch Case**
   - **Use Case**: Day of the week  
     ```java
     int day = 3;
     switch (day) {
         case 1: System.out.println("Monday"); break;
         case 2: System.out.println("Tuesday"); break;
         default: System.out.println("Other day");
     }
     ```

---

### **Loops**
1. **For Loop**
   - **Use Case**: Print numbers 1 to 5  
     ```java
     for (int i = 1; i <= 5; i++) {
         System.out.println(i);
     }
     ```

2. **While Loop**
   - **Use Case**: Countdown  
     ```java
     int count = 5;
     while (count > 0) {
         System.out.println(count);
         count--;
     }
     ```

3. **Do-While Loop**
   - **Use Case**: Ensure the block runs at least once  
     ```java
     int number = 1;
     do {
         System.out.println(number);
         number++;
     } while (number <= 5);
     ```

---

## **6. Arrays**
Store multiple values in one variable.  
- **Use Case**: Store marks of students.  
  ```java
  int[] marks = {85, 90, 78};
  for (int mark : marks) {
      System.out.println(mark);
  }
  ```

---

## **7. Methods (Functions)**
Reusable blocks of code.  
- **Example**:
  ```java
  public class Main {
      public static void main(String[] args) {
          greet("John");
      }

      public static void greet(String name) {
          System.out.println("Hello, " + name);
      }
  }
  ```

---

## **8. Object-Oriented Programming (OOP)**

### **Class and Object**
- **Example**:
  ```java
  class Car {
      String brand;
      int speed;

      public Car(String brand, int speed) {
          this.brand = brand;
          this.speed = speed;
      }

      public void display() {
          System.out.println("Brand: " + brand + ", Speed: " + speed);
      }
  }

  public class Main {
      public static void main(String[] args) {
          Car myCar = new Car("Toyota", 120);
          myCar.display();
      }
  }
  ```

### **Encapsulation**
- Use private fields with public methods.  
  ```java
  class Person {
      private String name;

      public String getName() {
          return name;
      }

      public void setName(String name) {
          this.name = name;
      }
  }
  ```

### **Inheritance**
- Extend properties of a class.  
  ```java
  class Animal {
      void eat() {
          System.out.println("This animal eats food.");
      }
  }

  class Dog extends Animal {
      void bark() {
          System.out.println("This dog barks.");
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

---

## **9. Exception Handling**
Handle runtime errors.  
- **Example**:
  ```java
  public class Main {
      public static void main(String[] args) {
          try {
              int result = 10 / 0;
          } catch (ArithmeticException e) {
              System.out.println("Cannot divide by zero.");
          }
      }
  }
  ```

---

## **10. Java Collections**
- Store and manipulate groups of objects.
- Example: `ArrayList`
  ```java
  import java.util.ArrayList;

  public class Main {
      public static void main(String[] args) {
          ArrayList<String> list = new ArrayList<>();
          list.add("Apple");
          list.add("Banana");

          for (String fruit : list) {
              System.out.println(fruit);
          }
      }
  }
  ```

---

## **11. File Handling**
Read and write to files.  
- **Example**: Write to a file
  ```java
  import java.io.FileWriter;
  import java.io.IOException;

  public class Main {
      public static void main(String[] args) {
          try {
              FileWriter writer = new FileWriter("output.txt");
              writer.write("Hello, Java!");
              writer.close();
          } catch (IOException e) {
              System.out.println("An error occurred.");
          }
      }
  }
  ```