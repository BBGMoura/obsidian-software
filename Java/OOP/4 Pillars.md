OOP and design is said to rest on the 3/4 pillars. These are:

1. Encapsulation
Encapsulation is distilling a concept down to a discrete set of data and behaviours. Encapsulation creates a new data type that's easy to understand and use.

Encapsulation is related to the [[SOLID |single responsibility principle]].

2. Inheritance
Inheritance is a form of code reuse. When a type `extends` another type, it incorporates all non-private super-class fields and methods as members. A subclass gains access to parent members without writing any code.

3. Polymorphism
When one or more subclasses override a super-class method or implement an interface, their behaviour us said to be polymorphic. All types have the same method signature, but the outcome differs between types.

4. Abstraction
Abstraction is the principle is the principle of revealing only the essential characteristics of a type. All the details are hidden in `private` fields and methods.

For example, the `Scanner` type's essential characteristics are its `next` and `hasNext` methods.

A beautiful abstraction makes complicated data types easy to use. For example, the `Random` class implements a pseudo-random number generation algorithm that's fairly complex.  All we have to worry about is `next()`, `nextInt()`, or any other `next` convenience method.