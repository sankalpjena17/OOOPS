## Access Modifiers 

Access modifiers in Java are keywords used before class names and class members (methods, constructors, and variables) to set their access levels and scope. The four access modifiers in Java are:


**1.Private**

**2.Default (no modifier)**

**3.Protected**

**4.Public**


### Private

**Scope:**  Accessible only within the class it is declared.

**Usage:**  Typically used for methods, fields, and constructors that should be hidden from the outside world.

**Example:**  A private field can be accessed only within its own class.


```ruby
private class Car{
    private String model;

    private void display(){
        System.out.println("The model is:" + model);
    }
}

```

In this example, both the model field and the display method are private, so they cannot be accessed from outside the Car class.


### Default (Package-Private) 

**Scope:**  No modifier is used, accessible within the same package.

**Usage:**  If no access modifier is specified, the member or class is visible to all classes within the same package.

**Example:**  Useful when you want package-wide access, but no visibility from other packages.

```ruby
class Helper(
    void helperMethod(){
        System.out.println("This is a default access method");
    }
)
```

The Helper class and the helpMethod method have package-level access and are not accessible from outside the package they are declared in.



### Protected

**Scope:**  Accessible within the same package or subclasses in different packages.

**Usage:**  Used when you want to allow a class member to be accessible to subclasses irrespective of their package.

**Example:**  Useful in inheritance when a base class needs to expose some methods or fields to its derived classes. 

```ruby
public class Animal{
    protected void display(){
        System.out.println("Iam an Animal");
    }
}

public class Dog extends Animal{
    public void printMsg(){
         display(); #Accessing protected method
    }
}
```

The display method is accessible within the Dog class, which is a subclass of Animal, even if it is in a different package.



### Public

**Scope:**  Accessible from any other class.

**Usage:**  Typically used for methods and variables that are intended to be accessed from any other class.

**Example:**  Most commonly used access level for public APIs of a class.

```ruby
public class PublicExample {
    public void publicMethod(){

    }
}
```
The publicMethod can be accessed from any other class in any package. 


### Summary of Accessibility

| Modifier     | Class | Package | Subclass (same pkg) | Subclass (diff pkg) | World |
|--------------|-------|---------|---------------------|---------------------|-------|
| public       | Y     | Y       | Y                   | Y                   | Y     |
| protected    | Y     | Y       | Y                   | Y                   | N     |
| no modifier  | Y     | Y       | Y                   | N                   | N     |
| private      | Y     | N       | N                   | N                   | N     |





## Constructor 


In Java, a constructor is a special type of method that is used to initialize objects. Here’s a detailed overview of constructors in Java, including their types and how they work:

### Basics of Constructors 


**Purpose:**  Constructors are primarily used to initialize an object's state. Unlike methods, constructors are called automatically when a new instance of an object is created.

**Name:**  The constructor must have the same name as the class itself.

**No Return Type:**  Constructors do not have a return type, not even void.


### Types of Constructors
 
#### Default Constructor

**Automatically Provided:**  If you do not explicitly define any constructor in your class, the Java compiler provides one for you. This default constructor is a no-argument constructor that calls the superclass's no-argument constructor.

``` ruby 
public class Animal {
    // Default constructor automatically created if no constructor is defined
}

```

#### No-Argument Constructor

**Explicit Definition:**  You can explicitly define a no-argument constructor. It is similar to the default constructor but can include additional initialization code.

``` ruby 
public class Animal{
    public Animal(){
        System.out.println("An animal is created");
    }
}
```

### Parameterized Constructor

**Initialization with Parameters:**  These constructors allow you to initialize your objects with specific values provided as parameters.

```ruby 
public class Animal {
    String name;
    public Animal(String name){
        this.name = name;
    }
}
```


### Constructor Overloading

**Multiple Constructors:**  Java allows you to have more than one constructor in a class, as long as each has a different parameter list (either different types or different number of parameters).

```ruby
public class Animal(){
    String name;
    int age;
    
    public Animal(){
        this.name = "Dog";
        this.age = age;
    }

    public Animal(String name){
        this.name = name;
    }
    
    public Animal(String name , int age){
        this.name = name;
        this.age = age;
    }
}
```


### Using this with Constructors

**Calling Another Constructor:**  Within a constructor, you can use this to call another constructor in the same class. This is useful for constructor chaining.

**Restrictions:**  The call to this() must be the first statement in a constructor.

``` ruby 
public class Animal{
    String name;
    int age;
    public Animal(){
        this("unkown" , 0); # calling parameterzed constructor
    }
    
    public Animal(String name , int age){
        this.name = name;
        this.age = age;
    }
}
```



### Superclass Constructor Calls

**Calling Superclass Constructor:**  If a class has a superclass, the constructor can call the superclass's constructor using super(). This call, if used, must also be the first statement in a constructor.

```ruby
public class Dog extends  Animal{
    public Dog(){
        super("Dog") #calling super clas's constructor
    }
}
```


Constructors are a fundamental aspect of object-oriented programming in Java, enabling explicit control over the initialization of objects.




