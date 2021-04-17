# Spring

![images](https://miro.medium.com/max/6076/1*gycg7f5bYLuR4ut_JAEs7A.png)

- Spring framework is an open source Java platform that provides comprehensive infrastructure support for developing robust Java applications very easily and very rapidly

## Applications of Spring
1. **POJO Based** 
    - Spring enables developers to develop enterprise-class applications using POJOs.
2.  **Modular** 
    - Spring is organized in a modular fashion. Even though the number of packages and classes are substantial, you have to worry only about the ones you need and ignore the rest
3. **Integration with existing frameworks**
    - Spring does not reinvent the wheel, instead it truly makes use of some of the existing technologies like several ORM frameworks, logging frameworks, JEE, Quartz and JDK timers, and other view technologies.
4. **Testablity**
    - Testing an application written with Spring is simple because environment-dependent code is moved into this framework. Furthermore, by using JavaBeanstyle POJOs, it becomes easier to use dependency injection for injecting test data
5. **Web MVC** 
    - Spring's web framework is a well-designed web MVC framework, which provides a great alternative to web frameworks such as Struts or other over-engineered or less popular web frameworks.
6. **Central Exception Handling** 
    - Spring provides a convenient API to translate technology-specific exceptions (thrown by JDBC, Hibernate, or JDO, for example) into consistent, unchecked exceptions.

7. **Lightweight**
    - Lightweight IoC containers tend to be lightweight, especially when compared to EJB containers, for example. This is beneficial for developing and deploying applications on computers with limited memory and CPU resources.

8. **Transaction management** 
    - Spring provides a consistent transaction management interface that can scale down to a local transaction (using a single database, for example) and scale up to global transactions (using JTA, for example).


## Getting Started with Spring 
- to start with spring you can follow this guide 
[Started with Spring](https://spring.io/guides)

## Spring MVC

![images](https://www.webcodein.com/wp-content/uploads/2019/11/selection-036-500x500.png)


- The Spring Web MVC framework provides Model-View-Controller (MVC) architecture and ready components that can be used to develop flexible and loosely coupled web applications
- define for each one of MVC:
1. **The Model** encapsulates the application data and in general they will consist of POJO.

2. **The View** is responsible for rendering the model data and in general it generates HTML output that the client's browser can interpret.

3. **The Controller** is responsible for processing user requests and building an appropriate model and passes it to the view for rendering.

- The Spring Web model-view-controller (MVC) framework is designed around a **DispatcherServlet** that handles all the HTTP requests and responses.

## DispatcherServlet

![images](https://huongdanjava.com/wp-content/uploads/2017/10/spring-mvc.png)





