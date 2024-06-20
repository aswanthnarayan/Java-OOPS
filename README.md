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


