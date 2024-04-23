## Interface 

In object-oriented programming (OOP), an interface is a fundamental concept used to define a contract for classes without providing the implementation of the methods it declares. Interfaces are essential for enforcing a certain set of functionalities across different classes, promoting a form of abstraction and multiple inheritance in languages like Java.


### Basics of Interfaces

An interface specifies what methods a class must implement, without specifying how these methods should be implemented. They are declared using the keyword interface in Java, C#, and several other programming languages.


```ruby
public interface Animal {
    void eat();
    void sleep();
}

```


### Characteristics of Interfaces

**Abstract Methods:**  All methods in interfaces are abstract by default, meaning they do not contain a body. The classes that implement the interface will provide the specific implementation of these methods.

**No Constructor:**  Interfaces cannot have constructors because interfaces cannot be instantiated on their own.

**Implementation:**  Any class that implements the interface must implement all its methods unless the class is declared abstract.

**Public Methods:**  In Java, all interface methods are public by default.



### Implementing Interfaces

Classes implement an interface by providing concrete implementations of the interface's abstract methods. A class can implement multiple interfaces, supporting a form of multiple inheritance.


```ruby
public class Dog implements Animal(){
    public void eat(){
        System.out.println("Dog eats");
    }
    public void sleep(){
        System.out.println("Dog sleeps");
    }
}
```


### Benefits of Using Interfaces

**Abstraction:**  Interfaces help in abstracting away the implementation details of classes and expose only the methods that other parts of the program can use.

**Multiple Inheritance:**  While Java does not support multiple inheritance with classes, it allows a class to implement multiple interfaces. This helps in avoiding the "diamond problem" of multiple inheritance.

**Loose Coupling:**  Interfaces aid in developing loosely coupled code which makes software easier to manage and modify.
Interoperability: Interfaces are crucial in establishing a common communication protocol between different systems.



## When to Use Interfaces

When multiple unrelated classes should provide certain functionality.
When you need to specify the behavior of a particular data type, but not concerned about who implements its behavior.
When you want to take advantage of multiple inheritance of type.




## Abstract class

### Definition and Purpose

An abstract class is a class that cannot be instantiated on its own and must be extended by other classes. It is intended to be a base class that other "concrete" classes can derive from. Abstract classes are used to capture shared characteristics of subclasses, while also allowing for specific behaviors to be defined in those subclasses.


### Characteristics of Abstract Classes

**Instantiation:**  Abstract classes cannot be instantiated directly. You must subclass them to create an instance.

**Abstract Methods:**  An abstract class can have abstract methods—methods without an implementation. These methods must be implemented by any subclass, unless the subclass is also declared abstract.

**Concrete Methods:**  Abstract classes can also have concrete methods (methods with an implementation). This allows an abstract class to provide default behavior that subclasses can inherit or override.

**Constructors:**  Unlike interfaces, abstract classes can have constructors. These constructors can be called by subclasses using the super() keyword.


```ruby
public abstract class Animal {
    public abstract void eat();

    public void breathe() {
        System.out.println("Breathing");
    }
}


public class Dog extends Animal {
    @Override
    public void eat() {
        System.out.println("Dog eats");
    }
}

```




## Interface VS Abstraction 


In programming, particularly in object-oriented languages like Java or C#, both abstract classes and interfaces are used to achieve abstraction, which allows for defining required structures while implementing actual functionalities in derived classes. 


### Abstract Class

**Definition:**  An abstract class is a class that cannot be instantiated on its own and must be inherited by other classes. It includes both abstract methods (which do not have an implementation and must be implemented by subclasses) and fully implemented methods.

**Purpose:**  Useful for sharing code among several closely related classes.

**Usage:**  Abstract classes can have constructors, and you can define methods with default implementations.

```ruby
public class Animal{
    #Abstract method doesnot have body
    public abstract void animalSound();

    #Regular method 
    public void sleep(){
        System.out.println("Zzz");
    }
}

class pig extends Animal{
    public void animalSound(){
        #The body of animalSound method is provieded here 
        System.out.println("The pig says : wee wee ");
    }
}

class main{
    public static void main(String [] args){
        pig myPig = new pig(); # created a pig object 
        myPig.animalSound();
        mypig.sleep();
    }
}
```




## Interface

**Definition:**  An interface is a completely "abstract class" that is used to group related methods with empty bodies. Starting from Java 8, interfaces can also contain default and static methods with implementations.

**Purpose:**  Used to indicate that classes share a certain behavior, often utilized for implementing multiple interfaces by a single class.

**Usage:**  Interfaces cannot have constructors and usually do not contain fields.

```ruby

interface Animal{
    #interface method doesnt have body 
    void animalSound();
    void sleep();
}

class pig implements Animal{
    public void animalSound(){
        #body of animalSound method is provided here 
        System.out.println("The pig says : wee wee ");
    }
    public void sleep(){
        System.out.println("The animal is sleeping");
    }
}

class Main{
    public static void main(String [] args){
        pig myPig  = new pig();
        myPig.animalSound();
        myPig.sleep();
    }
}
```



### Key Differences

**Multiple Inheritance:**  A class can implement multiple interfaces, but it can inherit from only one abstract class.

**Constructor:**  Abstract classes can have constructors, interfaces cannot.

**Method Type:**  Interfaces cannot have fully implemented methods (until Java 8, which introduced default methods), whereas abstract classes can mix fully implemented and abstract methods.

**Fields:**  Interfaces cannot have instance fields; all fields in an interface are public, static, and final by default. Abstract classes can have instance fields.



