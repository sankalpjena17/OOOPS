
## Inheritance 

Inheritance is a core concept in object-oriented programming (OOP) that allows one class to inherit properties and behaviors (methods) from another class. This feature helps to create a new class based on an existing class, which promotes reusability and can make the program structure more intuitive and easier to manage. Here's a detailed overview of inheritance, particularly focusing on Java, which can be applied to many other OOP languages as well:



### Concept and Definition

**Purpose:**  Inheritance enables a class to have the properties and methods of another class, enhancing reusability and enabling polymorphism.

**Superclass (Base or Parent class):**  The class whose properties and methods are inherited by another class.

**Subclass (Derived or Child class):**  The class that inherits properties and methods from another class.


### Syntax and Declaration

In Java, inheritance is declared using the extends keyword. A class can only extend (inherit from) one superclass because Java does not support multiple inheritance with classes (it does support multiple inheritance through interfaces).


```ruby
public class Animal{
    public void eat(){
        System.out.println("This Animal eats food");
    }
}

public class Dog extends Animal{
    public void bark(){
        System.out.println("This dog barks");
    }
}
```

In this example, Dog extends Animal, meaning Dog inherits the eat method from Animal.



### Types of Inheritance

**Single Inheritance:**  A subclass inherits from one superclass only.

**Multilevel Inheritance:**  A class extends another class, which in turn extends another class, forming a "chain" of inheritance (e.g., Child extends Parent, Parent extends Grandparent).


**Hierarchical Inheritance:**  One superclass is extended by multiple subclasses.


**Java avoids:** Multiple Inheritance (of classes): A class inheriting from more than one class. Java doesn't support this to avoid ambiguity issues such as the Diamond Problem. However, a class can implement multiple interfaces, which is Java's way of allowing multiple inheritance.




### Using the super Keyword

The super keyword in Java is used within a subclass to refer to the superclass's methods and constructors:


**Access Superclass Methods:**
```ruby
public void eat(){
    super.eats(); #Calls the eat method from Animal class
}
```


** Constructor Calls:

Superclass constructors are not inherited, but a subclass can call a superclass constructor using super().

This is often used to ensure proper initialization:

```ruby
public Dog() {
    super(); // Invoke the constructor of the superclass, Animal
}

```



### Method Overriding

Inheritance allows a subclass to override methods of its superclass, providing specific implementation details that replace the superclass's version.

```ruby
@Override
public void eat() {
    System.out.println("Dog eats dog food.");
}

```



### Access Levels and Inheritance

**Public:**  Members are accessible from any other class.

**Protected:**  Members are accessible within the same package or subclasses even if they are in different packages.

**Default (no modifier):**  Members are accessible only within the same package.

**Private:**  Members are not accessible directly by subclasses (can only be accessed via public or protected getters/setters).



### Benefits of Inheritance

**Reusability:**  Allows developers to reuse existing code.

**Extensibility:**  Makes it easy to make changes and additions to a program.

**Data Hiding:**  Parent class can keep some data private so it cannot be directly accessed by the subclass.

**Overriding Capability:**  Subclasses can tailor methods specific to their needs.



### Limitations of Inheritance

**Overuse:**  Improper use can lead to large, unwieldy class hierarchies that are difficult to manage.

**Tight Coupling:**  Changes in the superclass might require changes in subclasses.

**Inheritance vs Composition:**  Sometimes composition (using classes as instance variables) is more appropriate than inheritance, as it offers better encapsulation and flexibility.

Inheritance is a powerful OOP feature that, when used correctly, can significantly enhance the modularity, reusability, and maintainability of software.





### When to Use Inheritance

**Common Behavior with Variations:**  Use it when classes share many functionalities but also have their unique behaviors.

**Logical Hierarchical Relationships:**  Ideal for representing clear "is-a" relationships (e.g., Dog is an Animal).

**Polymorphism:**  Useful for implementing polymorphic behavior where different objects are accessed through the same interface.

**Extending Library Classes:**  Extend classes from libraries when modifying the original source is not possible, to add or enhance functionalities.



### When to Avoid Inheritance

**Non-subtype Relationships:**  Do not use inheritance if the subclass does not represent an "is-a" relationship with the superclass.

**High Flexibility Needs:**  Avoid it if superclass changes might affect subclasses, or if subclasses use only a small part of the superclass's functionality.

**Excessive Coupling: **Inheritance can tightly couple the superclass to its subclasses, making the system fragile and less modular.

**Functionality Restriction:** If the subclass should not inherently possess all the superclass's capabilities, inheritance might not be the best approach.





## Polymorphism

Polymorphism is a fundamental concept in object-oriented programming (OOP) that refers to the ability of different objects to respond to the same message (or method call) in different ways. The term "polymorphism" comes from the Greek words "poly" (meaning many) and "morph" (meaning form or shape), signifying that the same method can take on many forms.




#### Types of Polymorphism

#### Compile-time Polymorphism (Static Polymorphism):

**Method Overloading:**  This occurs when several methods exist with the same name but different parameters (different type or number of arguments) within the same class.

**Operator Overloading:**  This allows operators to have different implementations depending on their arguments (not supported in Java).

#### Runtime Polymorphism (Dynamic Polymorphism):

**Method Overriding:** This happens when a subclass has a method with the same name, return type, and parameters as a method in its superclass. The version of the method that is executed will depend on the type of the object that is used to invoke it, determined at runtime.



## Principles of Polymorphism

**Encapsulation:**  Hiding the details of how methods and data structures are implemented, allowing the same interface to be used for different underlying forms (data types).

**Inheritance:** Extending a class to create a new subclass provides a mechanism for reusing code and interfaces.



## Benefits of Polymorphism

**Simplifying Syntax:**  Allows methods to be called in the same way, even though they may behave differently based on the object that invokes them.

**Increasing Flexibility:**  Enables the implementation of one interface for multiple data types.

**Enhancing Maintainability:** Changes to the polymorphic code can be managed more efficiently. If a new object type is added, ensuring it adheres to the existing method interface will allow it to integrate with the existing system.

**Support for Open/Closed Principle:** Systems can be open for extension but closed for modification. New types can be introduced without changing the code that uses the base type.



In Java, polymorphism is primarily achieved through inheritance (using extends) and interfaces (using implements). Here’s how Java enables runtime polymorphism:

```ruby
class Animal{
    void sound(){
        System.out.println("Some sound");
    }
}

class Dog extends Animal{
    @Override
    void sound(){
        System.out.println("Bark");
    }
}

class Cat extends Animal {
    @Override
    void sounf(){
        System.out.println("Meow");
    }
}

public class TestPolymorphism {
    public static void main (String [] args){
        Animal myAnimal = new Animal();
        Animal myDog = new Dog();
        Animal myCat = new Cat();

        myAnimal.sound(); # Outputs: Some sound
        myDog.sound();    # Outputs: Bark
        myCat.sound();    # Outputs: Meow
    }
}
```

Animal is the superclass with a method sound().
Dog and Cat are subclasses that override the sound() method.
At runtime, Java VM determines which method to call based on the actual object type, not the reference type.



### When to Use Polymorphism

**Shared Interfaces:**  Useful when different classes perform the same function but require different implementations, adhering to a common interface.

**Code Reusability and Flexibility:**  Ideal for frameworks or libraries where different object types must be handled uniformly.

**Extending Functionality:**  Beneficial in systems designed for extension, allowing new types to integrate seamlessly.

**Reducing Complex Conditional Code:**  Replaces complex conditionals with a cleaner, polymorphic method structure.
When to Avoid Polymorphism

**Unnecessary Complexity:**  Avoid if the polymorphic behaviors are minimally used or if the system does not benefit significantly from interchangeable object behaviors.

**Performance Constraints:**  Not suitable for performance-critical sections where the overhead of dynamic dispatch could be detrimental.

**Limited Flexibility Requirements:**  Unnecessary in scenarios where objects do not need interchangeable behaviors or the application scale does not justify the complexity.

**Simple Applications:**  In smaller applications, the added complexity might not provide sufficient value.



### Compile-time

Compile-time refers to the phase in which the source code you write is translated into machine code by a compiler before the program is run. This phase is critical for catching syntax errors, type-checking errors, and other compile-time errors that can be detected before the program runs. It’s during this phase that the program is effectively "built."


### Runtime

Runtime refers to the period when the compiled program is actually running on the hardware. It begins when the program is started and terminates when the program ends. During runtime, the program interacts with the system’s hardware and resources to execute the compiled code.