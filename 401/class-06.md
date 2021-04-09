# Inheritance

![images](https://tutorials.supunkavinda.blog/static/images/php-oop-inheritance-2.png)

- Inheritance can be defined as the process where one class acquires the properties (methods and fields) of another.
- **Two type of classes**
    1. The class which inherits the properties of other is known as subclass (derived class, child class)
    2. the class whose properties are inherited is known as superclass (base class, parent class).

## extends Keyword
- to inherit the properties from another class we use **extends** keyword 

## The super keyword
- The super keyword is similar to this keyword. 
- it tell us that we can pass variable to super class or parent class.

- we can use super in two scenarios 
    1. It is used to differentiate the members of superclass from the members of subclass, if they have same names.
    2. It is used to invoke the superclass constructor from subclass.

## Types of Inheritance

![images](https://www.tutorialspoint.com/java/images/types_of_inheritance.jpg)


# Interfaces

![images](https://i0.wp.com/www.linuxandubuntu.com/wp-content/uploads/2020/01/Interfaces-in-Java.png?fit=1200%2C675)

- It is similar to class. It is a collection of abstract methods
- interface  contain constants, default methods, static methods, and nested types
- Writing an interface is similar to writing a class
- interface contains behaviors that a class implements.


- An interface is similar to a class in the following ways

    1. An interface can contain any number of methods.

    2. An interface is written in a file with a .java extension, with the name of the interface matching the name of the file.

    3. The byte code of an interface appears in a .class file.

    4. Interfaces appear in packages, and their corresponding bytecode file must be in a directory structure that matches the package name.

- However, an interface is different from a class in several ways, including −

    1. You cannot instantiate an interface.

    2. An interface does not contain any constructors.

    3. All of the methods in an interface are abstract.

    4. An interface cannot contain instance fields. The only fields that can appear in an interface must be declared both static and final.

    5. An interface is not extended by a class; it is implemented by a class.

    6. An interface can extend multiple interfaces.


## Declaring Interfaces
- The interface keyword is used to declare an interface.

- it has the following properties
    1. An interface is abstract. You do not need to use the abstract keyword while declaring an interface.

    2. Each method in an interface is also abstract, so the abstract keyword is not needed.

    3. Methods in an interface are  public

## Implementing Interfaces
- use the **implements** keyword to implement an interface.

## Difference Between abstract and interface
![images](https://cdn.journaldev.com/wp-content/uploads/2013/07/abstract-class-vs-interface.png)