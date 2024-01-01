An interface is an abstract "class" that is used to group related methods with "empty" bodies.  To access the interface methods, the interface must be implemented with the `implements` keyword (Like extends for inheritance).

```java
public interface Vehicle {
    void accelerate();
}
```

Classes which implements the interface must override all of its methods. 

## Interfaces as Types
Interfaces are Java data types, just like classes and primitives.  They ca n be used as parameter and declared as part of an array. For examples if we create classes which implement the `Vehicle`  class. We can collect all the objects into a `Vehicle[]` array.

### Why and when to use Interfaces?
To achieve security - hide certain details and only show the important details of an object (interface). For example, refer to the interface in the code instead of the object.

Java does not support "multiple inheritance" (a class can only inherit from one superclass). However, it can be achieved with interfaces, because the class can **implement** multiple interfaces. **Note:** To implement multiple interfaces, separate them with a comma (see example below).

Rule #1: Use an interface when there are two or more concrete implementations that solve one problem.  For example, Visa, Discover, and American Express resolve payments in completely different ways. Their implementations are different.

Rule #2: Use an interface when one concrete implementation solves a problem but there's a possibility of different implementations. For example, we might create a game that's initially limited to human players. If there's a possibility of an AI player in the future, add a `Player` interface to establish the player contract.

Rule #3: Use an interface to control testing. (This is a preview rule. We'll cover testing soon.)