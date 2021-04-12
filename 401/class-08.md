

# SOLID

![images](https://miro.medium.com/max/5018/1*1Fl0dq4B7vq3zqR2k8bHdg.jpeg)

- five principles of Object-Oriented class design
- They are a set of rules and best practices to follow while designing a class structure.
-  the SOLID acronym, they are:
    1. The Single Responsibility Principle
    2. The Open-Closed Principle
    3. The Liskov Substitution Principle
    4. The Interface Segregation Principle
    5. The Dependency Inversion Principle


## The Single Responsibility Principle
- The Single Responsibility Principle states that a class should do one thing and therefore it should have only a single reason to change.
- it is important, because many different teams can work and edit same project this could lead to incompatible modules
- it makes version control easier

## Open-Closed Principle
- The Open-Closed Principle requires that classes should be open for extension and closed to modification.
- Modification means changing the code of an existing class
- extension means adding new functionality.
- We should be able to add new functionality without touching the existing code for the class
- to add new functionality without touching the class by help of interfaces and abstract classes.

## Liskov Substitution Principle
- The Liskov Substitution Principle states that subclasses should be substitutable for their base classes.
- This is the expected behavior, because when we use inheritance we assume that the child class inherits everything that the superclass has. The child class extends the behavior but never narrows it down

## Interface Segregation Principle
- Segregation means keeping things separated, and the Interface Segregation Principle is about separating the interface
-  Clients should not be forced to implement a function they do no need.

## Dependency Inversion Principle
- The Dependency Inversion principle states that our classes should depend upon interfaces or abstract classes instead of concrete classes and functions