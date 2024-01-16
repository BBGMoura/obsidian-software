Dependency Injection is  a crucial pattern in software development and is present in production-ready frameworks like Spring. 

Spring promotes loose coupling between classes, improves testability and facilitates modularity.

There are three ways to do Dependency Injection using the Spring Framework:
- Field Injection uses reflection to set the values of private attributes/fields.
- Setter Injection uses public setters to set the value of the attributes/fields.
- Constructor  Injection happens at the time of creating the object itself.

## Field Injection
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

## Dependency Inversion (D from [[SOLID]])

