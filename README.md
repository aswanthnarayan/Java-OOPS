## Object

An object is a real-world entity that has both state and behavior. State refers to the data or attributes of the object, while behavior refers to the methods or functions it can perform.

### Constructor

A constructor is a special method used to initialize an object. It has the same name as the class and does not have a return type. There are two types of constructors:

- **Default Constructor**: Initializes the object with default values.
   
- **Parameterized Constructor**: Allows you to specify initial values for the object's attributes during object creation.

### Copy Constructor

A copy constructor is a special type of parameterized constructor that takes another object of the same class as a parameter and initializes the new object with the values of the provided object.

#### Example

```java
public class Dog {
    // Instance variables
    String name;
    String breed;
    int age;

    // Default constructor
    public Dog() {
        // Initializing instance variables with default values
        this.name = "Unknown";
        this.breed = "Unknown";
        this.age = 0;
    }

    // Parameterized constructor
    public Dog(String name, String breed, int age) {
        this.name = name;
        this.breed = breed;
        this.age = age;
    }

    // Copy constructor
    public Dog(Dog other) {
        this.name = other.name;
        this.breed = other.breed;
        this.age = other.age;
    }

    // Method
    void bark() {
        System.out.println(name + " is barking");
    }
}

// Main class
public class Main {
    public static void main(String[] args) {
        // Creating an object using the default constructor
        Dog defaultDog = new Dog();
        defaultDog.bark(); // Output: Unknown is barking

        // Creating an object using the parameterized constructor
        Dog parameterizedDog = new Dog("Buddy", "Golden Retriever", 5);
        parameterizedDog.bark(); // Output: Buddy is barking

        // Creating a copy of an existing object using the copy constructor
        Dog copiedDog = new Dog(parameterizedDog);
        copiedDog.bark(); // Output: Buddy is barking
    }
}
```


## Class

    Class is a Blue print to create an Object ,It defines the attributes (States) and methods (behaviors) 

# 4 PILLERS OF OOPS

## 1. Inheritance

Inheritance is a mechanism that allows a child class to inherit methods and attributes from a parent class. There are four types of inheritance:
1. **Single Inheritance**: A class inherits from one parent class.
2. **Multilevel Inheritance**: A class is derived from another class, which is also derived from another class.
3. **Hierarchical Inheritance**: Multiple classes inherit from a single superclass.
4. **Multiple Inheritance**: A class can inherit from multiple classes. (Note: Java does not support multiple inheritance with classes directly but can achieve it with interfaces.)

### Example

```java
 package com.example;

public class Car {

    void starting(String brand) {
        System.out.println(brand + " starting");
    }

    public static void main(String[] args) {
        System.out.println("Hello world!");
    }
}


public class Electric extends Car {

    public static void main(String[] args) {
        Electric tesla = new Electric();
        tesla.starting("Tesla");
    }
}
```
## 2.Encapsulation
Binding of Data/variable to the method in the same class is called encapsulation ,So no one can access the data/variable from out side of the class.To access the variable need to access through Getter and Setter methods ,Its help to data hiding

ex:
```java
  package com.example;

class Human {
    private String name;
    private int age;

    // Setter methods
    public void setName(String name) {
        this.name = name;
    }

    public void setAge(int age) {
        this.age = age;
    }

    // Getter methods
    public String getName() {
        return name;
    }

    public int getAge() {
        return age;
    }
}

public class Demo {
    public static void main(String[] args) {
        Human person1 = new Human();
        person1.setName("Aswanth");
        person1.setAge(26);
        System.out.println("My Name is " + person1.getName() + " I am " + person1.getAge() + " years old");
    }
}
```
### "this" Keyword
 this is the keyword that represent current object 

## 3.Polymorphism
Polymorphism that allows methods to process objects differently based on their data type or class
There are two main types of polymorphism in Java
- **Compile-time Polymorphism**:
    - Achieved through method overloading and operator overloading.
    - Determined at compile time.

- **Run-time Polymorphism**:
    - Achieved through method overriding.
    - Determined at runtime

### Method Overloading
This occurs when multiple methods in the same class have the same name but different parameters (different type, number, or both).

        ex:
```java
class MathUtils {
    // Method to add two integers
    int add(int a, int b) {
        return a + b;
    }

    // Method to add three integers
    int add(int a, int b, int c) {
        return a + b + c;
    }

    // Method to add two doubles
    double add(double a, double b) {
        return a + b;
    }
}

public class Main {
    public static void main(String[] args) {
        MathUtils math = new MathUtils();
        System.out.println(math.add(5, 10));       // Calls add(int, int)
        System.out.println(math.add(5, 10, 15));   // Calls add(int, int, int)
        System.out.println(math.add(5.5, 10.5));   // Calls add(double, double)
    }
}
```
###  2.Method Overriding:
This occurs when a subclass has a method with the same name, return type, and parameters as a method in its superclass. The method in the 
        subclass overrides the method in the superclass.

        ex:
```java

class Animal {
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    @Override
    void sound() {
        System.out.println("Dog barks");
    }
}

class Cat extends Animal {
    @Override
    void sound() {
        System.out.println("Cat meows");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal myDog = new Dog();
        Animal myCat = new Cat();

        myDog.sound(); // Calls Dog's sound() method
        myCat.sound(); // Calls Cat's sound() method
    }
}
```

## 4.Abstraction
Abstraction is the concept of hiding the complex implementation details of a system and showing only the essential features to the user
Abstraction in Java can be achieved using:

### Abstract Classes
An abstract class is a class that cannot be instantiated on its own and may contain abstract methods, which are methods without a body.
        Subclasses of the abstract class must provide implementations for the abstract methods.

        ex: 
```java
   abstract class Vehicle {
    // Abstract method (does not have a body)
    abstract void start();

    // Concrete method
    void stop() {
        System.out.println("Vehicle stopped.");
    }
}

class Car extends Vehicle {
    @Override
    void start() {
        System.out.println("Car started.");
    }
}

public class Main {
    public static void main(String[] args) {
        Vehicle myCar = new Car();
        myCar.start(); // Outputs: Car started.
        myCar.stop();  // Outputs: Vehicle stopped.
    }
}
```
        
### 2.interface
An interface in Java is a reference type, similar to a class, that can contain only constants, method signatures, default methods, static methods,and nested types. Interfaces cannot contain instance fields or method implementations. A class that implements an interface must provide implementationsfor all the methods declared in the interface.
            
      ex:
```java
              interface Animal {
    void sound();
    void eat();
}

class Dog implements Animal {
    @Override
    public void sound() {
        System.out.println("Dog barks");
    }

    @Override
    public void eat() {
        System.out.println("Dog eats");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal myDog = new Dog();
        myDog.sound(); // Outputs: Dog barks
        myDog.eat();   // Outputs: Dog eats
    }
}
```

### Super Method
Every constructor in java already have a default method called super().it lies on first line inside any constructor .when we executing the code,it calls the default constructor of parent class

### Access Modifiers

Access modifiers in Java are keywords used to set the accessibility or visibility of classes, variables, methods, and constructors. They control which other classes can access a particular class member. Java provides several access modifiers, each with its own level of visibility and restrictions:

1. **Public**: Public members are accessible from any other class. There are no restrictions on accessing public members.

2. **Protected**: Protected members are accessible within the same package and by subclasses (even if they are in different packages).

3. **Default (Package-private)**: Members with no explicit access modifier (i.e., no modifier keyword) are considered package-private. They are accessible only within the same package.

4. **Private**: Private members are accessible only within the same class. They are not visible to subclasses or other classes.

Exception handling in Java
Exception handling is handle unexpected errors using try catch method

    ex:
```java
try {
    // Code that may throw an exception
} catch (ExceptionType1 ex1) {
    // Handle exception of type ExceptionType1
} catch (ExceptionType2 ex2) {
    // Handle exception of type ExceptionType2
} finally {
    // Code that will be executed regardless of whether an exception occurred
}
```

### Final vs Finally Keywords

#### Final
`final` is a keyword used to create constants, prevent method overriding, or prevent class inheritance. Basically, if we use the `final` keyword before a class, we cannot create a subclass of that class.

#### Finally
`finally` is a block used in exception handling to execute cleanup tasks that must be performed regardless of whether an exception occurred or not.

