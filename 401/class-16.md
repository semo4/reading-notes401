# Spring Security Architecture

![images](https://www.techbooky.com/wp-content/uploads/2019/09/Spring-Security-Architecture.jpg) 

- This guide is a primer for Spring Security, offering insight into the design and basic building blocks of the framework. However, in doing so, we can clear up some of the confusion experienced by developers who use Spring Security. Use this guide when you need a high-level understanding of how a secure application works, how it can be customized, or if you need to learn how to think about application security.

- Sometimes people say «access control» instead of «authorization», which can get confusing, but it can be helpful to think of it that way because «authorization» is overloaded in other places. Spring Security has an architecture that is designed to separate authentication from authorization and has strategies and extension points for both.

## Authentication

![images](https://github.com/spring-guides/top-spring-security-architecture/raw/master/images/authentication.png)

- The main strategy interface for authentication is AuthenticationManager, which has only one method:

- An AuthenticationManager can do one of 3 things in its authenticate() method:

    1. Return an Authentication (normally with authenticated=true) if it can verify that the input represents a valid principal.

    2. Throw an AuthenticationException if it believes that the input represents an invalid principal.

    3. Return null if it cannot decide.

- AuthenticationException is a runtime exception. In other words, user code is not normally expected to catch and handle it. The most commonly used implementation of AuthenticationManager is ProviderManager, which delegates to a chain of AuthenticationProvider instances.

## Customizing Authentication Managers
- The most commonly used helper is the AuthenticationManagerBuilder, which is great for setting up in-memory, JDBC, or LDAP user details or for adding a custom UserDetailsService.

- If we had used an Override of a method in the configurer, the AuthenticationManagerBuilder would be used only to build a «local» AuthenticationManager, which would be a child of the global one. Spring Boot provides a default global AuthenticationManager unless you pre-empt it by providing your own bean of type AuthenticationManager. If you do any configuration that builds an AuthenticationManager, you can often do it locally to the resources that you are protecting and not worry about the global default

## Authorization or Access Control
- Once authentication is successful, we can move on to authorization, and the core strategy here is AccessDecisionManager
- The Object is completely generic in the signatures of the AccessDecisionManager and AccessDecisionVoter. It represents anything that a user might want to access . ConfigAttribute is an interface. It has only one method , so these strings encode in some way the intention of the owner of the resource, expressing rules about who is allowed to access it. Most people use the default AccessDecisionManager, which is AffirmativeBased .
- This is supported by an AccessDecisionVoter that can handle the expressions and create a context for them.

## Web Security

![images](https://github.com/spring-guides/top-spring-security-architecture/raw/master/images/filters.png)

- At most, one servlet can handle a single request, but filters form a chain, so they are ordered. Spring Security is installed as a single Filter in the chain, and its concrete type is FilterChainProxy, for reasons that we cover soon. In a Spring Boot application, the security filter is a @Bean in the ApplicationContext, and it is installed by default so that it is applied to every request.

- There can be multiple filter chains all managed by Spring Security in the same top level FilterChainProxy and all are unknown to the container. The Spring Security filter contains a list of filter chains and dispatches a request to the first chain that matches it.

![images](https://github.com/spring-guides/top-spring-security-architecture/raw/master/images/security-filters.png)


- A vanilla Spring Boot application with no custom security configuration has a several filter chains, where usually n=6.

![images](https://github.com/spring-guides/top-spring-security-architecture/raw/master/images/security-filters-dispatch.png)

## Creating and Customizing Filter Chains
- You can switch it off completely by setting security.basic.enabled=false, or you can use it as a fallback and define other rules with a lower order. To do the latter, add a @Bean of type WebSecurityConfigurerAdapter and decorate the class with @Order.

- Many applications have completely different access rules for one set of resources compared to another. Each set of resources has its own WebSecurityConfigurerAdapter with a unique order and its own request matcher.

## Request Matching for Dispatch and Authorization
- A security filter chain has a request matcher that is used to decide whether to apply it to an HTTP request. However, within a filter chain, you can have more fine-grained control of authorization by setting additional matchers in the HttpSecurity configure

## Combining Application Security Rules with Actuator Rules
- If you use the Spring Boot Actuator for management endpoints, you probably want them to be secure, and, by default, they are. It is defined with a request matcher that matches only actuator endpoints and it has an order of ManagementServerProperties.BASIC_AUTH_ORDER, which is 5 fewer than the default SecurityProperties fallback filter, so it is consulted before the fallback.

## Method Security
- If Spring creates a @Bean of this type, it is proxied and callers have to go through a security interceptor before the method is actually executed. If access is denied, the caller gets an AccessDeniedException instead of the actual method result. There are other annotations that you can use on methods to enforce security constraints, notably @PreAuthorize and @PostAuthorize, which let you write expressions containing references to method parameters and return values, respectively.

## Working with Threads
- The basic building block is the SecurityContext, which may contain an Authentication .
- The type of the Principal in an Authentication is dependent on the AuthenticationManager used to validate the authentication, so this can be a useful little trick to get a type-safe reference to your user data.

## Processing Secure Methods Asynchronously
- Since the SecurityContext is thread-bound, if you want to do any background processing that calls secure methods , you need to ensure that the context is propagated. This boils down to wrapping the SecurityContext with the task that is executed in the background. Spring Security provides some helpers to make this easier, such as wrappers for Runnable and Callable.
