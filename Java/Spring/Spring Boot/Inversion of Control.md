Spring Boot is an inversion of control framework. These are design patterns that are used to remove dependency from programming code. They make the code easier to test and maintain.

Example:

- [c]  
``` java
class Employee {
	Address address;
	Employee(){
		address = new Address();
	}
}
```
This creates a a tight coupling. The creation of employee is dependant on the creation of address.

- [p] 

In the inversion of control scenario, we do something like:

``` java
class Employee {
	Address address;
	Employee(Address address){
		this.address = address
	}
}
```

This makes the code loosely coupled. There is no need to modify the code if the logic moves to a new environment. This is dependency injection.

In Spring framework, IOC container is responsible to inject the dependency. We provide metadata to the IOC container either by XML file or annotation.