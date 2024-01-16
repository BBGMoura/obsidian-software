The SOLID acronym presents a set of design principles for improving object-oriented code.

## Single Responsibility Principle
Each class should only have one responsibility and it should not reappear again in another class. Only one class should have to change if a responsibility changes. This means this class has good [[4 Pillars| Encapsulation]].

## Open-close Principle
A class should be open for extension but closed for modification. Once a concept that represents a single responsibility has been encapsulated, development should stop. If further responsibility is required, it should be added to a class that uses the original class. This extends the class's capabilities without modifying the class.

## Liskov Substitution Principle
If a super-class is required, any subclass of that type should satisfy the requirement without inspecting the subclass.  All subclasses should be adequate replacements for required type.

## Interface Segregation Principle
Use many small specific interfaces instead of one large general interface.

## Dependency Inversion Principle
Classes should rely on abstractions, not implementations. When possible, it's better to provide a super-class or interface as a class dependency. It provides flexible since any subclass can be swapped for another.