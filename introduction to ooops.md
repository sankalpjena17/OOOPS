## Introduction to oops 
Object-Oriented Programming (OOP) is a programming paradigm based on the concept of "objects," which can contain data and code: data in the form of fields (often known as attributes or properties), and code, in the form of procedures (often known as methods).



## Core Concepts of OOP
**1.Encapsulation:** This is the practice of keeping fields within a class private, then providing access to them via public methods. It's a protective barrier that keeps the data and code safe within the object and prevents outside interference and misuse.

**2.Inheritance:** This is a way to form new classes using classes that have already been defined. The new classes, known as derived classes, inherit attributes and behaviors from the existing classes, which are called base classes. It allows for a hierarchy of classes that share a set of attributes and methods.

**3.Polymorphism:** This means having many forms. In OOP, polymorphism refers to the ability of a variable, function, or object to take on multiple forms. The most common use of polymorphism is when a parent class reference is used to refer to a child class object.

**4.Abstraction:** This is the concept of hiding the complex reality while exposing only the necessary parts. It helps in handling complexity by hiding unnecessary details from the user. That enables the user to implement more complex logic on top of the provided abstraction without understanding or even thinking about all the hidden complexity.



## Benefits of OOP
**Modularity:** The source code for an object can be written and maintained independently of the source code for other objects. Once created, an object can be easily passed around inside the system.

**Reusability:** Objects can also be reused within an across applications. The reuse of software also lowers the cost of development. More effort is put into the object-oriented analysis and design, which lowers the overall cost of development.

**Pluggability and Debugging Ease:** If a particular object turns out to be problematic, it can simply be removed from the application and plugged in a different object as its replacement. This is analogous to fixing mechanical parts in machines.

**Enhanced Software Maintenance:** Objects can be maintained separately, making locating and fixing problems easier and faster.



## Example in Java
Here's a basic example to illustrate how OOP works using a class and objects:
```ruby
public class Dog {
    // Fields (attributes)
    private String name;
    private int age;

    // Constructor
    public Dog(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // Method (behavior)
    public void bark() {
        System.out.println(name + " says: Bark bark!");
    }

    // Getter method
    public String getName() {
        return name;
    }

    // Setter method
    public void setName(String name) {
        this.name = name;
    }
}

public class Main {
    public static void main(String[] args) {
        // Create a Dog object
        Dog myDog = new Dog("Rover", 5);
        myDog.bark(); // Outputs: Rover says: Bark bark!

        // Access the Dog object's attributes and methods
        System.out.println("This dog's name is " + myDog.getName());
        myDog.setName("Max");
        myDog.bark(); // Outputs: Max says: Bark bark!
    }
}

```

In this example, Dog class has fields (name, age), a constructor, and methods (bark, getName, setName). Objects are created and manipulated in Main class. This demonstrates encapsulation (using private fields and public methods), and the methods bark, getName, and setName provide a simple interface for interacting with the object.
