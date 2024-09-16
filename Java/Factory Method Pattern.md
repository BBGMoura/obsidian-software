A Factory method pattern is a creational design pattern. It provides an interface for creating objects in a superclass, but allows subclasses to alter the type of objects that need to be created.

## Problem
You have created a logistics management application. The first version of the app can only handle transportation by trucks.

After a while, you have demand to add Ships to the application. However, the logic is coupled with Truck class.

## Solution
Replace direct object construction calls (using `new` operator) with calls to the special factory method. Objects return from factory method are usually referred to as products.

![[Pasted image 20240915175502.png]]

This way, you can override the factory method in a subclass and change the class of products being created by the method. 

Sub classes may return different types of products only if these products have a common base.![[Pasted image 20240915175747.png]]

So in this example, Truck and Ship would implement the Transport interface.

## Structure
![[Pasted image 20240915175900.png]]

1. The **product** declares the interface. Common base to all objects can be produced by the creator and its subclass.
2. **Concrete Products** are implemented differently using the product interface.
3. **Creator** class declares the factory method that returns new product objects. The return type of of this method matches the product interface.