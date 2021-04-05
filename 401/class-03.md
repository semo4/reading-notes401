# Maps, primitives, File I/O

## Primitives versus Objects

![images](https://slideplayer.com/5151059/16/images/slide_1.jpg)

- Java has a two-fold type system consisting of primitives such as int, boolean and reference types such as Integer, Boolean. Every primitive type corresponds to a reference type.
- Every object contains a single value of the corresponding primitive type.

##  Single Item Memory Footprint
- each of data type has size that can impact to the memory
    - boolean – 1 bit
    - byte – 8 bits
    - short, char – 16 bits
    - int, float – 32 bits
    - long, double – 64 bits

## Memory Footprint for Arrays
- the data type in array are more expensive 
    - long, double: m(s) = 128 + 64 s
    - short, char: m(s) = 128 + 64 [s/4]
    - byte, boolean: m(s) = 128 + 64 [s/8]
    - the rest: m(s) = 128 + 64 [s/2]

## Performance
- the primitive types live in the stack while the reference types live in the heap. This is a dominant factor that determines how fast the objects get be accessed.

## Default Values
Default values of the primitive types are:
    -  0 for numeric types
    - false for the boolean type
    - \u0000 for the char type.
    - wrapper classes, the default value is null.


## Usage
- primitive types are much faster and require much less memory


# Exceptions

![images](https://techvidvan.com/tutorials/wp-content/uploads/sites/2/2020/04/types-of-java-exception-1200x675.jpg)

- is a problem that arises during the execution of a program. When an Exception occurs the normal flow of the program is disrupted and the program/Application terminates abnormally.

An exception can occur for many different reasons:
1. A user has entered an invalid data.
2. A file that needs to be opened cannot be found.
3. A network connection has been lost in the middle of communications or the JVM has run out of memory.

## The Catch or Specify Requirement
- A method catches an exception using a combination of the try and catch keywords. A try/catch block is placed around the code that might generate an exception. Code within a try/catch block is referred to as protected code
- A try block can be followed by multiple catch blocks

## Throw Exceptions
- You can throw an exception, either a newly instantiated one or an exception that you just caught, by using the throw keyword.

## Advantages of Exceptions
1. Separating Error-Handling Code from "Regular" Code
2. Propagating Errors Up the Call Stack
3. Grouping and Differentiating Error Types


# Scanning

![images](https://www.edureka.co/blog/wp-content/uploads/2019/08/scanner-class-in-java-1.jpg)

- Scanner class in Java is found in the java.util package. The Java Scanner class breaks the input into tokens using a delimiter which is whitespace by default. The Java Scanner class is widely used to parse text for strings and primitive types using a regular expression. It is the simplest way to get input in Java.
