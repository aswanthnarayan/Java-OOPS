# Object

An object is a real-world entity that has both state and behavior. State refers to the data or attributes of the object, while behavior refers to the methods or functions it can perform.

## Constructor

A constructor is a special method used to initialize an object. It has the same name as the class and does not have a return type. There are two types of constructors:

- **Default Constructor**: Initializes the object with default values.
   
- **Parameterized Constructor**: Allows you to specify initial values for the object's attributes during object creation.

## Copy Constructor

A copy constructor is a special type of parameterized constructor that takes another object of the same class as a parameter and initializes the new object with the values of the provided object.

### Example

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
