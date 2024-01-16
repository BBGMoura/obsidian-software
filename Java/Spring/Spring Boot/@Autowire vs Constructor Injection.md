Dependency Injection is  a crucial pattern in software development and is present in production-ready frameworks like Spring. 

Spring promotes loose coupling between classes, improves testability and facilitates modularity.

There are three ways to do Dependency Injection using the Spring Framework:
- Field Injection uses reflection to set the values of private attributes/fields.
- Setter Injection uses public setters to set the value of the attributes/fields.
- Constructor  Injection happens at the time of creating the object itself.

# Field Injection
Field Injection is achieved by adding the **@Autowire** annotation to a class field. It allows the automatic wiring of the dependency.  

Auto-wiring (**@Autowire**) is one of the most commonly seen anti-patterns in codebases that use Spring IoC/DI Framework. 

- [p] Why it is used:
- Easy to use
- Short and sweet

- [c] Why it should not be used:
- Coupling
- Bad test experience
- Hidden dependencies

**@Autowire** alone is not the root of all evil. The key is _where_ you are using it. Most of the time, it is used at the field/attribute level. Using it at the setter method can reduce the damage, but not eliminate all of it.

**@Autowire** violates some good code design principle.

### Dependency Inversion (D from [[SOLID]])
 If you want to use the class outside the application container. For example, for unit testing, you are forced to use a Spring container to instantiate your class as there are no other ways to set the @Autowire fields.

Therefore, no point of injection exists.

### Single Responsibility Principle  (S from [[SOLID]])
Single Responsibility Principle (SRP)  states that a class should _have only one reason to change_. A class should only have one responsibility or concern. **@Autowired** itself does not violate this. 

If a class has multiple responsibilities and dependencies through the annotation, it could be a violation of the SRP. In this case, it might be ideal to refactor into separate classes.

Otherwise, if constructor-based dependency is used, as more dependencies are added the constructor will grow too big.

## Complexity
**@Autowire** can make the code more complex. Especially when dealing with circular dependencies.  When tow or more classes depend on each other, it becomes hard to determine the order in which they should be instantiated. 

This is hard to debug and can lead to runtime errors.

# Constructor Injection
We should use  **Constructor Injection** instead. 

Example:
``` Java
@Component
public class Calculator {
   private Multiplier multiplier;
   // Default constructor. It will be used by Spring to 
   // inject the dependencies declared here.
   public Calculator(Multiplier multiplier) {
      this.multiplier = multiplier;
   }
}
```

The dependency between the two components are explicitly declared the code design allows a mock instance of Multiplier to be injected at runtime.

Also, Construction injection helps in creating immutable objects. This is because the constructor is the only way to create new objects. Once we create a bean, we cannot alter it's dependencies anymore.

On the other hand, setter injection allows dependency injection after creation. This creates mutable objects, which are not thread-safe in a multi-threaded environment.
