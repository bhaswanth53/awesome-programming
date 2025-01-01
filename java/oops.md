### **Object-Oriented Programming (OOP) in Java**
OOP is a programming paradigm based on the concept of **objects**. These objects contain **data** (fields) and **methods** (functions) to manipulate the data. Java is built on OOP principles.

---

### **Four Core OOP Principles**
1. **Encapsulation**  
2. **Inheritance**  
3. **Polymorphism**  
4. **Abstraction**

---

#### **1. Encapsulation**
Encapsulation means wrapping data (variables) and methods (functions) together into a single unit (class) and restricting direct access to some of the object's components.  

**Use Case**: Protect sensitive data.  
**Example**:
```java
// File location: src/com/example/Person.java
package com.example;

public class Person {
    private String name; // Private variable

    // Public getter
    public String getName() {
        return name;
    }

    // Public setter
    public void setName(String name) {
        this.name = name;
    }
}
```

**Accessing Encapsulated Data:**
```java
// File location: src/com/example/Main.java
package com.example;

public class Main {
    public static void main(String[] args) {
        Person person = new Person();
        person.setName("Alice"); // Setting value
        System.out.println(person.getName()); // Getting value
    }
}
```

---

#### **2. Inheritance**
Inheritance allows one class to acquire properties (fields and methods) from another.  

**Use Case**: Reuse code across related classes.  

**Example**:
```java
// File location: src/com/example/Animal.java
package com.example;

public class Animal {
    public void eat() {
        System.out.println("This animal eats food.");
    }
}

// File location: src/com/example/Dog.java
package com.example;

public class Dog extends Animal { // Dog inherits Animal
    public void bark() {
        System.out.println("This dog barks.");
    }
}

// File location: src/com/example/Main.java
package com.example;

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.eat(); // Inherited method
        dog.bark(); // Dog's own method
    }
}
```

---

#### **3. Polymorphism**
Polymorphism means "many forms." In Java, it allows methods to perform different tasks based on the object that invokes them.  
- **Compile-time Polymorphism** (Method Overloading)
- **Runtime Polymorphism** (Method Overriding)

**Use Case**: Implement flexible and reusable code.  

**Method Overloading Example**:
```java
// File location: src/com/example/Calculator.java
package com.example;

public class Calculator {
    public int add(int a, int b) {
        return a + b;
    }

    public double add(double a, double b) { // Overloaded method
        return a + b;
    }
}
```

**Method Overriding Example**:
```java
// File location: src/com/example/Shape.java
package com.example;

public class Shape {
    public void draw() {
        System.out.println("Drawing a shape");
    }
}

// File location: src/com/example/Circle.java
package com.example;

public class Circle extends Shape {
    @Override
    public void draw() {
        System.out.println("Drawing a circle");
    }
}

// File location: src/com/example/Main.java
package com.example;

public class Main {
    public static void main(String[] args) {
        Shape shape = new Circle();
        shape.draw(); // Output: Drawing a circle
    }
}
```

---

#### **4. Abstraction**
Abstraction hides implementation details and shows only functionality to the user. It is achieved using **abstract classes** and **interfaces**.

**Abstract Class Example**:
```java
// File location: src/com/example/Vehicle.java
package com.example;

public abstract class Vehicle {
    public abstract void start(); // Abstract method
}

// File location: src/com/example/Car.java
package com.example;

public class Car extends Vehicle {
    @Override
    public void start() {
        System.out.println("Car starts with a key.");
    }
}
```

---

### **Imports and Exports in Java**
Java organizes its code into **packages**. To use classes from one package in another, we use the `import` keyword.

#### **Importing Classes**
1. **Single Class Import**
   ```java
   import com.example.Person; // Imports only the Person class
   ```

2. **Wildcard Import**
   ```java
   import com.example.*; // Imports all classes in the package
   ```

#### **Exporting Classes**
Exporting classes simply means making them accessible by defining them as `public` and placing them in a package structure.

---

### **File Handling Example**
Let’s create an example that demonstrates **file locations**, **imports**, and **exports** with file handling.

1. **Write to a File**
```java
// File location: src/com/example/FileWriterExample.java
package com.example;

import java.io.FileWriter;
import java.io.IOException;

public class FileWriterExample {
    public void writeToFile(String fileName, String content) {
        try {
            FileWriter writer = new FileWriter(fileName);
            writer.write(content);
            writer.close();
            System.out.println("File written successfully.");
        } catch (IOException e) {
            System.out.println("An error occurred.");
        }
    }
}
```

2. **Read from a File**
```java
// File location: src/com/example/FileReaderExample.java
package com.example;

import java.io.FileReader;
import java.io.BufferedReader;
import java.io.IOException;

public class FileReaderExample {
    public void readFromFile(String fileName) {
        try {
            FileReader reader = new FileReader(fileName);
            BufferedReader br = new BufferedReader(reader);
            String line;
            while ((line = br.readLine()) != null) {
                System.out.println(line);
            }
            br.close();
        } catch (IOException e) {
            System.out.println("An error occurred.");
        }
    }
}
```

3. **Main Class**
```java
// File location: src/com/example/Main.java
package com.example;

public class Main {
    public static void main(String[] args) {
        FileWriterExample writer = new FileWriterExample();
        FileReaderExample reader = new FileReaderExample();

        String fileName = "src/output.txt";
        String content = "Hello, this is a file handling example in Java!";

        writer.writeToFile(fileName, content);
        reader.readFromFile(fileName);
    }
}
```

---

### **Explanation of File Locations**
- **`src/com/example/FileWriterExample.java`**: Contains the class for writing to a file.
- **`src/com/example/FileReaderExample.java`**: Contains the class for reading from a file.
- **`src/com/example/Main.java`**: The main program that imports and uses the file handling classes.

When executed, the program will:
1. Create a file named `output.txt` in the `src` folder.
2. Write the specified content to the file.
3. Read the file content and display it in the console.

---