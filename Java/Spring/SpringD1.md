## IOC & DI
IoC (Inversion of Control)  
In contrast with traditional programming, in which our custom code makes calls to a library, IoC enables a framework to take control of the flow of a program and make calls to our custom code.    
The advantages of this architecture are:
- decoupling the execution of a task from its implementation
- making it easier to switch between different implementations
- greater modularity of a program
- greater ease in testing a program by isolating a component or mocking its dependencies, and allowing components to communicate through contracts
DI (Dependency Injection)
Dependency injection is a pattern we can use to implement IoC, where the control being inverted is setting an object's dependencies.

## Bean Scopes
The scope of a bean defines the life cycle and visibility of that bean in the contexts we use it.
The latest version of the Spring framework defines 6 types of scopes:
- singleton  (most important)
When we define a bean with the singleton scope, the container creates a single instance of that bean; all requests for that bean name will return the same object, which is cached. Any modifications to the object will be reflected in all references to the bean. This scope is the default value if no other scope is specified.
- prototype  
A bean with the prototype scope will return a different instance every time it is requested from the container. 
- request
- session
- application
- websocket  
All four above are Web Aware Scopes. We use these less often in practice.

## POJO
Plain Old Java Object  
When we talk about a POJO, what we're describing is a straightforward type with no references to any particular frameworks. A POJO has no naming convention for our properties and methods.
```java
public class EmployeePojo {

    public String firstName;
    public String lastName;
    private LocalDate startDate;

    public EmployeePojo(String firstName, String lastName, LocalDate startDate) {
        this.firstName = firstName;
        this.lastName = lastName;
        this.startDate = startDate;
    }

    public String name() {
        return this.firstName + " " + this.lastName;
    }

    public LocalDate getStart() {
        return this.startDate;
    }
}
```

可以通过三种不同的方式定义Spring bean：(主要用前两种)  
使用构造型@Component注释（或其衍生物）注释你的类  
编写在自定义Java配置类中使用@Bean注释的bean工厂方法  
在XML配置文件中声明bean定义  
Here we are going to discuss how to create a Spring Bean in 3 different ways as follows: 
- Creating Bean Inside an XML Configuration File (beans.xml)
- Using @Component Annotation
- Using @Bean Annotation
```java
// Java Program to Illustrate College Class

package ComponentAnnotation;

// Importing required classes
import org.springframework.stereotype.Component;

@Component("collegeBean")

// Class
public class College {

	// Method
	public void test()
	{
		// Print statement
		System.out.println("Test College Method");
	}
}
```
```java
// Java Program to Illustrate Configuration in College Class

package BeanAnnotation;

// Importing required classes
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;

@Configuration
public class CollegeConfig {

	// Using Bean annotation to create
	// College class Bean
	@Bean

	// Here the method name is the
	// bean id/bean name
	public College collegeBean()
	{

		// Return the College object
		return new College();
	}
}
```